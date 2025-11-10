<script lang="ts">
	import NavStructure from './nav-structure.svelte';
	import NavVoiles from './nav-voiles.svelte';
	import NavCodes from './nav-codes.svelte';
	import NavArchitecture from './nav-architecture.svelte';
	import NavMain from './nav-main.svelte';
	import NavSecondary from './nav-secondary.svelte';
	import * as Sidebar from '$lib/components/ui/sidebar/index.js';
	import type { ComponentProps } from 'svelte';
	import {
		IconBook,
		IconBug,
		IconFlame,
		IconLock,
		IconLockAccess,
		IconPackage,
		IconDatabase,
		IconFileText,
		IconUpload,
		IconDownload,
		IconAppWindow,
		IconList,
		IconLogin,
		IconLogout,
		IconUsers
	} from '@tabler/icons-svelte';

	const data = {
		navMain: [
			{
				title: 'Home',
				url: '/docs'
			}
		],

		
		structure: [
			{
				name: 'Coque',
				url: '/docs/StructureFlottante/Coque'
			},
			{
				name: 'Flotteurs',
				url: '/docs/StructureFlottante/Flotteur'
			},
			{
				name: 'Baie de capteur',
				url: '/docs/StructureFlottante/BaieDeCapteur'
			},
			{
				name: 'Dérive',
				url: '/docs/StructureFlottante/Derive'
			},
			{
				name: 'Gouvernail',
				url: '/docs/StructureFlottante/Gouvernail'
			},
			{
				name: 'Études',
				url: '/docs/StructureFlottante/Etudes'
			},
		],


		voiles: [
			{
				name: 'Voiles',
				url: '/docs/VoilesMats/Voile'
			},
			{
				name: 'Mâts',
				url: '/docs/VoilesMats/Mat'
			},
			{
				name: 'Construction',
				url: '/docs/VoilesMats/Construction'
			},
			{
				name: 'Études',
				url: '/docs/VoilesMats/Etudes'
			},
		],

		architecture: [
			{
				name: 'Architecture système',
				url: '/docs/ArchitectureSysteme/SystemArchitecture'
			},
			{
				name: 'Électricité',
				url: '/docs/ArchitectureSysteme/Electricite'
			},
			{
				name: 'Équipements',
				url: '/docs/ArchitectureSysteme/Equipement'
			},
		],

		codes: [
			{
				name: 'Code commande volet',
				url: '/docs/Codes/CommandeVolets'
			},
		],

		navSecondary: [
			{
				title: 'Issues',
				url: 'https://github.com/code-gio/svelte-firekit/issues'
			}
		],
	};

	let { ...restProps }: ComponentProps<typeof Sidebar.Root> = $props();
</script>

<Sidebar.Root collapsible="offcanvas" {...restProps}>
	<Sidebar.Header>
		<Sidebar.Menu>
			<Sidebar.MenuItem>
				<Sidebar.MenuButton class="data-[slot=sidebar-menu-button]:!p-1.5">
					{#snippet child({ props })}
						<a href="/" {...props}>
							<span class="text-base font-semibold">HydroSharks</span>
						</a>
					{/snippet}
				</Sidebar.MenuButton>
			</Sidebar.MenuItem>
		</Sidebar.Menu>
	</Sidebar.Header>
	<Sidebar.Content>
		<NavMain items={data.navMain} />
		<NavStructure items={data.structure} />
		<NavVoiles items={data.voiles} />
		<NavArchitecture items={data.architecture} />
		<NavCodes items={data.codes} />
	</Sidebar.Content>
	<Sidebar.Footer>
		<NavSecondary items={data.navSecondary} />
	</Sidebar.Footer>
</Sidebar.Root>
