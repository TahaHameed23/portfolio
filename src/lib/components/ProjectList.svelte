<script lang="ts">
	import ProjectLink from './ProjectLink.svelte';

	const projects = [
		{
			href: 'https://datafloww.onrender.com',
			title: 'Datafloww',
			description:
				'web analytics platform for tracking & analyzing website traffic, user behavior, & engagement metrics.'
		},
		{
			href: 'https://appread.appwrite.network',
			title: 'Appread',
			description:
				'a web application that allows users to read and manage their favorite articles, blogs, and news content in one place.'
		}
	];
</script>

<section>
	<div class="mb-4 text-lg sm:text-xl lg:text-2xl">My works:</div>
	<div>
		{#each projects as project}
			<ProjectLink {...project} />
		{/each}
	</div>
</section>
