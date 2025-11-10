<script lang="ts">
	import * as Sidebar from '$lib/components/ui/sidebar/index.js';
	let { items }: { items: { name: string; url: string}[] } = $props();
	const sidebar = Sidebar.useSidebar();
</script>

<Sidebar.Group>
	<Sidebar.GroupLabel>Structure flottante</Sidebar.GroupLabel>
	<Sidebar.Menu>
		{#each items as item (item.name)}
			<Sidebar.MenuItem>
				<Sidebar.MenuButton>
					{#snippet child({ props })}
						<a {...props} href={item.url}>
							<span>{item.name}</span>
						</a>
					{/snippet}
				</Sidebar.MenuButton>
			</Sidebar.MenuItem>
		{/each}
	</Sidebar.Menu>
</Sidebar.Group>
