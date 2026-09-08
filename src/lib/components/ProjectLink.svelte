<script lang="ts">
	let { href, title, description } = $props<{
		href: string;
		title: string;
		description: string;
	}>();
</script>

<article class="mt-4 first:mt-0">
	<a
		{href}
		target="_blank"
		rel="noopener noreferrer"
		class="text-xl tracking-normal underline underline-offset-3 ease-in-out hover:underline hover:decoration-dashed hover:underline-offset-3 sm:text-2xl lg:text-3xl"
		>{title}</a
	>
	<p class="mt-2 text-base sm:text-lg lg:text-lg">{description}</p>
</article>
