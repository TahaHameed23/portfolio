<script lang="ts">
	import { fly } from 'svelte/transition';
</script>

<section in:fly={{ y: 10 }} class="mt-36 mb-20 tracking-wider lg:mt-36 lg:mb-90 lg:tracking-wide">
	<p class="mb-1 text-3xl leading-tight sm:text-4xl lg:text-7xl">Software Engineer</p>
	<p class="text-base leading-snug font-light sm:text-xl lg:text-3xl">
		cloud, databases & distributed systems
	</p>
</section>
