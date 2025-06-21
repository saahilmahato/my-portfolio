<script>
	import Section from '$lib/components/Section.svelte';
	import ExperienceCard from '$lib/components/ExperienceCard.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CardView from '$lib/components/CardView.svelte';

	const headlineText = 'Experience';
	const subHeadlineText = "Frontend? Backend? Infra? If it compiles (eventually), I'm in. 🦾";

	const experiences = [
		{
			role: 'Software Engineer',
			company: 'Cedar Gate Technologies',
			duration: 'Dec 2024 - Present',
			description:
				'Currently upgrading a healthcare analytics platform with modern frameworks and resolving a large volume of security vulnerabilities to improve system integrity and compliance.'
		},
		{
			role: 'Software Engineer',
			company: 'Leapfrog Technology',
			duration: 'Jan 2022 - Oct 2024',
			description:
				'Contributed to healthcare projects involving complex business logic, including prescription processing workflows and drug discovery pipelines.'
		}
	];
</script>

<Section id="experience">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<CardView>
		{#each experiences as job (job.company)}
			<ExperienceCard
				role={job.role}
				company={job.company}
				duration={job.duration}
				description={job.description}
			/>
		{/each}
	</CardView>
</Section>
