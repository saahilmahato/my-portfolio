<script>
	import Section from '$lib/components/Section.svelte';
	import InfoCard from '$lib/components/InfoCard.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CardView from '$lib/components/CardView.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';

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

	const nextSection = 'education';
	const nextSectionlabel = 'Academic Lore';

	const scrollText = 'Scroll for academic trauma (and triumph) ↓';
</script>

<Section id="experience">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />

	<CardView>
		{#each experiences as job (job.company)}
			<InfoCard
				title={job.role}
				institution={job.company}
				duration={job.duration}
				description={job.description}
			/>
		{/each}
	</CardView>

	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
