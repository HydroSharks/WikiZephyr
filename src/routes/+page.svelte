<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import {
		Card,
		CardContent,
		CardDescription,
		CardHeader,
		CardTitle
	} from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Tabs, TabsContent, TabsList, TabsTrigger } from '$lib/components/ui/tabs/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
	import {
		IconBolt,
		IconShield,
		IconDatabase,
		IconUpload,
		IconUsers,
		IconCode,
		IconRocket,
		IconCheck,
		IconArrowRight,
		IconStar,
		IconBrandGithub,
		IconPackage,
		IconPlayerPlay,
		IconBook,
		IconSettings,
		IconGlobe,
		IconDeviceMobile,
		IconServer
	} from '@tabler/icons-svelte';
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
	<link rel="canonical" href="https://hydrosharks.eu/" />
	
	<!-- Open Graph -->
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Wiki Zéphyr" />
	<meta property="og:description" content="Le wiki officiel du projet Zéphyr par l'association HydroSharks" />
	<meta property="og:url" content="https://hydrosharks.eu/" />
	<meta property="og:site_name" content="Wiki Zéphyr" />
	<meta property="og:image" content="https://hydrosharks.eu/logo.svg" />
	<meta property="og:image:width" content="1200" />
	<meta property="og:image:height" content="630" />
	<meta property="og:image:alt" content="Wiki Zéphyr" />
	

	<!-- Organization structured data -->
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "SoftwareApplication",
			"name": "Wiki Zéphyr",
			"description": "Le wiki officiel du projet Zéphyr par l'association HydroSharks",
			"url": "https://hydrosharks.eu/docs/",
			"applicationCategory": "DeveloperApplication",
			"operatingSystem": "Any",
			"programmingLanguage": "TypeScript",
			"author": {
				"@type": "Person",
				"name": "Giovanni Rodriguez",
				"url": "https://github.com/code-gio"
			},
			"offers": {
				"@type": "Offer",
				"price": "0",
				"priceCurrency": "EUR"
			},
			"codeRepository": "https://github.com/Fabien-Math/testwiki"
		}
	</script>
	
	<!-- Website structured data -->
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "WebSite",
			"name": "Svelte FireKit",
			"url": "https://hydrosharks.eu/docs/",
			"potentialAction": {
				"@type": "SearchAction",
				"target": {
					"@type": "EntryPoint",
					"urlTemplate": "https://hydrosharks.eu/docs?q={search_term_string}"
				},
				"query-input": "required name=search_term_string"
			}
		}
	</script>
</svelte:head>

<div class="min-h-screen">
	<!-- Hero Section -->
	<section class="relative overflow-hidden">
		<div class="relative mx-auto max-w-7xl px-4 pt-20 pb-16 sm:px-6 lg:px-8">
			<div class="text-center">
				<h1 class="mb-6 text-5xl font-bold text-slate-900 md:text-6xl dark:text-white">
					Hydro<span class="text-[#3DD1F2]">Sharks</span>
				</h1>

				<p class="mx-auto mb-8 max-w-3xl text-xl text-slate-600 dark:text-slate-300">
					Le wiki officiel du projet Zéphyr
				</p>

				<div class="mb-12 flex flex-col justify-center gap-4 sm:flex-row">
					<Button size="lg" href="/docs">
						<IconPlayerPlay />
						Get Started
					</Button>

					<Button variant="outline" size="lg" href="https://github.com/Fabien-Math/testwiki">
						<IconBrandGithub />
						GitHub
					</Button>
				</div>


				
				<img src="/images/logo/WindOfChangeCroppedBlurred.png" width=1200 title="WindOfChange" alt="WindOfChange">

			</div>
		</div>
	</section>
</div>
