<script lang="ts">
	let {
		title = 'Portfolio',
		isDark = false,
		onToggleTheme
	} = $props<{
		title?: string;
		isDark?: boolean;
		onToggleTheme?: () => void;
	}>();

	const navLinks = [
		{ href: '/writings', label: 'Writings' },
		{ href: '/papershelf', label: 'Papershelf' }
	];

	let scrollY = $state(0);
</script>

<svelte:window bind:scrollY />

<header
	class="sticky top-0 z-25 -mx-4 w-[calc(100%+2rem)] border-b border-black/5 px-4 py-4 transition-all duration-300 lg:-mx-20 lg:w-[calc(100%+10rem)] lg:px-20 lg:py-5 lg:backdrop-blur-lg dark:border-white/10"
	class:backdrop-blur={scrollY > 0}
>
	<div class="flex w-full items-center gap-2 lg:gap-4">
		<a href="/" class="min-w-0 shrink truncate text-sm font-semibold lg:text-lg">{title}</a>

		<div class="ml-auto flex shrink-0 items-center gap-2 lg:gap-4">
			<nav
				class="flex flex-nowrap items-center gap-2 text-xs whitespace-nowrap lg:gap-4 lg:text-base"
			>
				{#each navLinks as link}
					<a
						href={link.href}
						class="text-current no-underline transition hover:underline hover:decoration-dashed hover:underline-offset-2"
						>{link.label}</a
					>
				{/each}
			</nav>

			<button
				type="button"
				onclick={onToggleTheme}
				class="inline-flex size-10 shrink-0 items-center justify-center rounded-full bg-transparent text-current transition hover:cursor-pointer hover:bg-olive-300 hover:duration-300 lg:size-11 dark:hover:bg-gray-700"
				aria-label="Toggle theme"
				aria-pressed={isDark}
			>
				{#if isDark}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						stroke="currentColor"
						stroke-width="2"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="lucide lucide-sun-icon lucide-sun"
					>
						<circle cx="12" cy="12" r="4" />
						<path d="M12 2v2" />
						<path d="M12 20v2" />
						<path d="m4.93 4.93 1.41 1.41" />
						<path d="m17.66 17.66 1.41 1.41" />
						<path d="M2 12h2" />
						<path d="M20 12h2" />
						<path d="m6.34 17.66-1.41 1.41" />
						<path d="m19.07 4.93-1.41 1.41" />
					</svg>
				{:else}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						stroke="currentColor"
						stroke-width="2"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="lucide lucide-moon-icon lucide-moon"
					>
						<path
							d="M20.985 12.486a9 9 0 1 1-9.473-9.472c.405-.022.617.46.402.803a6 6 0 0 0 8.268 8.268c.344-.215.825-.004.803.401"
						/>
					</svg>
				{/if}
			</button>
		</div>
	</div>
</header>
