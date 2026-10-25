<script lang="ts">
	import ProfileIntro from '$lib/components/ProfileIntro.svelte';
	import ProjectList from '$lib/components/ProjectList.svelte';
	import SocialLinks from '$lib/components/SocialLinks.svelte';
</script>

<ProfileIntro />

<div
	class="mt-12 mb-12 flex flex-col gap-8 text-base lg:mt-16 lg:mb-16 lg:flex-row lg:items-start lg:gap-72 lg:text-lg"
>
	<section class="lg:w-11/12">
		<p class="mb-4 text-base leading-relaxed sm:text-lg lg:text-2xl">
			I'm a software engineer from India who learns & builds websites at scale. I have experience
			with web technologies (full stack), primarily focused on backend development. I enjoy working
			with cloud, databases and distributed systems. I also love to work, develop and contribute in
			open source projects.
		</p>
	</section>

	<SocialLinks />
</div>

<section>
	<div class="mb-28 sm:text-xl lg:text-xl">
		I'm currently working at Cognizant as a Programmer Analyst
	</div>
</section>

<ProjectList />

<section class="mt-12 mb-12 lg:mt-16 lg:mb-16 lg:text-lg">
	<div>
		Here's a resource list I have curated:
		<a
			href="https://taha-hameed.notion.site/Learning-repository-8307485b5eb047aca354af66b6e1b2b8"
			class="text-blue-500 hover:underline hover:decoration-dashed hover:underline-offset-3"
			target="_blank">learning repository</a
		>
	</div>
</section>
