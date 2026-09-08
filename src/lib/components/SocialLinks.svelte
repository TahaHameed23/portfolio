<script lang="ts">
	const socialLinks = [
		{ href: 'https://linkedin.com/in/tahahameed', label: 'LinkedIn' },
		{ href: 'https://github.com/tahahameed23', label: 'GitHub' },
		{ href: 'https://x.com/tahahameed_', label: 'X' }
	];
</script>

<section class="lg:w-1/2">
	<p class="mb-3">Find me on:</p>
	<ul class="list-numbering space-y-1 text-sm sm:text-base lg:text-lg">
		{#each socialLinks as link}
			<li>
				<a
					href={link.href}
					target="_blank"
					rel="noopener noreferrer"
					class="hover:underline hover:decoration-dashed">{link.label}</a
				>
			</li>
		{/each}
	</ul>
</section>
