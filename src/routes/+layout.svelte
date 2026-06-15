<script lang="ts">
	import './layout.css';
	import '@fontsource-variable/space-grotesk/wght.css';
	import favicon from '$lib/assets/icon/favicon.ico';
	import Header from '$lib/components/Header.svelte';
	import { browser } from '$app/environment';
	import { env } from '$env/dynamic/public';

	const analyticsScriptSrc = env.PUBLIC_ANALYTICS_SCRIPT_URL ?? 'http://localhost:3000/script.js';
	const analyticsWebsiteId =
		env.PUBLIC_ANALYTICS_WEBSITE_ID ?? 'a542cd07-0a69-47f1-b4ea-18903aae5866';

	let { children } = $props();
	let isDark = $state(
		browser
			? ((window as Window & { __theme?: 'dark' | 'light' }).__theme ?? 'dark') === 'dark'
			: true
	);

	function applyTheme(dark: boolean) {
		isDark = dark;

		if (typeof document !== 'undefined') {
			document.documentElement.classList.toggle('dark', dark);
			document.documentElement.style.colorScheme = dark ? 'dark' : 'light';
		}

		if (typeof localStorage !== 'undefined') {
			localStorage.setItem('theme', dark ? 'dark' : 'light');
		}

		if (typeof window !== 'undefined') {
			(window as Window & { __theme?: 'dark' | 'light' }).__theme = dark ? 'dark' : 'light';
		}
	}

	function toggleTheme() {
		applyTheme(!isDark);
	}
</script>

<svelte:head
	><link rel="icon" href={favicon} />
	<script defer src={analyticsScriptSrc} data-website-id={analyticsWebsiteId}></script>
</svelte:head>
<div
	class="min-h-screen bg-olive-200 px-4 text-slate-900 transition-colors duration-300 selection:bg-orange-500 selection:text-white lg:px-20 dark:bg-black dark:text-gray-100"
>
	<div class="fixed top-0 left-0 z-50 h-1 w-full bg-orange-500"></div>
	<Header title="Taha Hameed" {isDark} onToggleTheme={toggleTheme} />
	<main class="py-6 pb-12 lg:py-8 lg:pb-16">
		{@render children()}
	</main>
</div>
