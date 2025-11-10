<script lang="ts">
	import DocRenderer from '$lib/components/docs/doc-renderer.svelte';
	import type { PageData } from './$types.js';
	import { page } from '$app/stores';

	let { data }: { data: PageData } = $props();
	let title = $derived(data.metadata.title);
	let description = $derived(data.metadata.description);
	let slug = $derived(data.metadata.slug);
	let url = $derived(`https://svelte-firekit.com${$page.url.pathname}`);
</script>

<svelte:head>
	<title>Wiki Zéphyr</title>
	<meta
		name="description"
		content="Le wiki officiel du projet Zéphyr par l'association HydroSharks"
	/>
	<meta
		name="keywords"
		content="HydroSharks, hydro, hydrosharks, trimaran, autonome, autonomous, navire, voilier, sailboat, étudiant, zéphyr, Zéphyr, recherche, bateau, plateforme, projet"
	/>
	<!-- Canonical URL -->
	<link rel="canonical" href={url} />
	
	<!-- Open Graph -->
	<meta property="og:type" content="article" />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:url" content={url} />
	<meta property="og:site_name" content="Wiki Zéphyr" />
	<meta property="og:image" content="https://svelte-firekit.com/logo.svg" />
	<meta property="og:image:width" content="1200" />
	<meta property="og:image:height" content="630" />
	<meta property="og:image:alt" content="Wiki Zéphyr - {title}" />
	
	<!-- Article structured data -->
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "TechArticle",
			"headline": "{title}",
			"description": "{description}",
			"url": "{url}",
			"dateModified": "{data.metadata.lastModified || new Date().toISOString()}",
			"author": {
				"@type": "Person",
				"name": "Giovanni Rodriguez",
				"url": "https://github.com/code-gio"
			},
			"publisher": {
				"@type": "Organization",
				"name": "HydroSharks",
				"logo": {
					"@type": "ImageObject",
					"url": "https://hydrosharks.eu"
				}
			},
			"mainEntityOfPage": {
				"@type": "WebPage",
				"@id": "{url}"
			}
		}
	</script>
</svelte:head>

<DocRenderer {title} {description} {data} />
