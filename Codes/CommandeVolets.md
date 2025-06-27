---
sort: 1
---

# Commande volet

Les volets sont commandés à l’aide de vérins déjà acquis par l’association. Le mouvement de translation du vérin est transformé en rotation du mât du volet grâce à un système de poulies et de cordes (voir [Voiles](../VoilesMats/Voile.md#système-de-commande-volet)). Afin de vérifier la faisabilité de ce mécanisme, un code Python a été développé pour calculer l’allongement de la corde en fonction de l’angle du volet. 
La relation entre l’angle du volet et la longueur de la corde est probablement non linéaire, car elle dépend de fonctions trigonométriques telles que le cosinus et le sinus.

Ce code comprend une partie calcul et une partie affichage. Le calcul de la longueur de la corde en fonction de l’angle est réalisé de manière discrète ; une fonction continue pourrait être déterminée, mais cela n’a pas été jugé nécessaire dans ce cas. Pour la commande des volets, une telle fonction sera probablement requise.



## Code


```python
import numpy as np
from matplotlib.animation import FuncAnimation
import matplotlib.pyplot as plt
plt.rcParams.update({"font.size": 12, "figure.autolayout":True, "figure.figsize": (12.7, 7.2)})

plt.style.use('dark_background')
# plt.style.use('seaborn')
# plt.style.use('ggplot')

def distance(u:tuple, v:tuple) -> float:
	"""Compute Euclidian distance between two points"""
	return np.sqrt(np.sum((v - u)**2))


#####   CALCULATION   #####
# x = 0.060
# y = 0.066
# r = 0.096

# Constants (system value)
d = 0.066	# Unmoveable	
e = -0.036
rr = 0.096	# Unmoveable
radius = 0.015

# Constants (improved value)
# e = - 0.085

# Limit angle we want
limits = 30

# Array of angle reachable in deg and rad
alpha = np.linspace(-limits, limits, 1000)
alpha_rad = np.radians(alpha)

# Geometry
s1m_pos = np.array((-rr, 0))
s1u_ptf = np.array((e, d))
s1d_ptf = np.array((e, -d))
pivot_pos = (0.0, 0.0)

dus = []
dds = []
for angle_rad in alpha_rad:
	rota_matrix = np.array([[np.cos(angle_rad), -np.sin(angle_rad)], [np.sin(angle_rad), np.cos(angle_rad)]])

	s1m_ptf = np.matmul(rota_matrix, s1m_pos - pivot_pos) + pivot_pos

	dus.append(distance(s1u_ptf, s1m_ptf))
	dds.append(distance(s1d_ptf, s1m_ptf))

dus = np.array(dus)
dds = np.array(dds)
offset = dus[len(dus)//2] + dds[len(dds)//2]

print(f"Max streching: {abs(min(dus + dds - offset)) + abs(max(dus + dds - offset)):.3e} m")
print(f"Max streching: {(abs(min(dus + dds - offset)) + abs(max(dus + dds - offset)))/ offset*100:.1f} %")



#####   DISPLAY   #####

### Geometry
plt.title("String lengths againt desired angle")
plt.plot(alpha, dus, label="Top string")
plt.plot(alpha, dds, label="Bottom string")
plt.xlabel(r"$\alpha$ (deg)")
plt.ylabel("String length (m)")
plt.legend()
plt.show()

### Difference
plt.title("Length of the overall string againt desired angle")
plt.ylabel("Streched string length (m)")
plt.xlabel(r"$\alpha$ (deg)")
plt.plot(alpha, dus  + dds - offset)
plt.legend()
plt.show()


### Scheme and animated plot
back = 0
middle = 500
front = 1000

flap = plt.Rectangle((-0.15, -0.001), 0.5, 0.002, rotation_point=pivot_pos, color="dimgrey", zorder=back)


pivot = plt.Circle((0, 0), radius, color="dimgrey", zorder=back)
pivot_centre = plt.Circle((0, 0), radius/10, color="red", zorder=front)

string1_up = plt.Circle(s1u_ptf, radius/10, color="lightblue", zorder=front)
string1_down = plt.Circle(s1d_ptf, radius/10, color="lightblue", zorder=front)
string1_mid = plt.Circle(s1m_pos, radius/10, color="lightblue", zorder=front)

fig, ax = plt.subplots(2, 1)

ax[0].add_patch(flap)
ax[0].add_patch(pivot)
ax[0].add_patch(pivot_centre)
ax[0].add_patch(string1_down)
ax[0].add_patch(string1_up)
ax[0].add_patch(string1_mid)

line1, = ax[0].plot([], [], color="lightblue")
line2, = ax[0].plot([], [], color="lightblue")
ax[0].set_title("Scheme of the flap movement")
ax[0].set_xlabel("X Position (m)")
ax[0].set_ylabel("Y Position (m)")
ax[0].axis("equal")
# ax[0].set_ylim(-0.064, 0.064)

cursor, = ax[1].plot([], [], marker='o', markersize=10, color="red", zorder=front)
ax[1].plot(alpha, dus + dds - offset, color="green", zorder=middle)
ax[1].grid(ls='-.', alpha=0.5)
ax[1].set_title("Difference in total string length")
ax[1].set_xlabel(r"$\alpha$ (deg)")
ax[1].set_ylabel("Length Difference (m)")

def update(frame):
	angle = frame
	angle_rad = np.radians(angle)
	rota_matrix = np.array([[np.cos(angle_rad), -np.sin(angle_rad)], [np.sin(angle_rad), np.cos(angle_rad)]])
	
	s1m_ptf = np.matmul(rota_matrix, s1m_pos - pivot_pos) + pivot_pos
	
	du = distance(s1u_ptf, s1m_ptf)
	dd = distance(s1d_ptf, s1m_ptf)
	
	string1_up.center = s1u_ptf
	string1_down.center = s1d_ptf
	string1_mid.center = s1m_ptf
	
	line1.set_data((s1d_ptf[0], s1m_ptf[0]), (s1d_ptf[1], s1m_ptf[1]))
	line2.set_data((s1u_ptf[0], s1m_ptf[0]), (s1u_ptf[1], s1m_ptf[1]))
	flap.angle = angle

	
	line1.set_label(f"Top string length: {du:.4f} m")
	line2.set_label(f"Bottom string length: {dd:.4f} m")
	ax[0].legend(loc='upper right')

	# Update the plot for the sum of both lengths
	total_length = du + dd - offset
	cursor.set_label(f"Angle: {angle:.1f}°\nLength difference: {total_length:.2e} m")
	cursor.set_data(angle, total_length)
	ax[1].legend()
	

ani = FuncAnimation(fig, update, frames=np.concatenate([np.linspace(0, limits, 50), np.linspace(limits, -limits, 100), np.linspace(-limits, 0, 50)]), interval=50)

plt.show()

```