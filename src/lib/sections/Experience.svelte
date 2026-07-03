<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import ExperienceView from '$lib/components/ExperienceView.svelte';

	const headlineText: string = 'Experience';
	const subHeadlineText: string =
		"Frontend? Backend? Infra? If it compiles (eventually), I'm in. 🦾";

	const experiences: Array<object> = [
		{
			id: 1,
			role: 'Software Development Enginner 2 (SDE-II)',
			company: 'IQVIA',
			duration: 'Jan 2026 - Present',
			description:
				'Working on a generative AI feature that lets users query the analytics engine in natural language and receive accurate data, implementing RAG-based retrieval.'
		},
		{
			id: 2,
			role: 'Software Engineer',
			company: 'Cedar Gate Technologies',
			duration: 'Dec 2024 - Jan 2026',
			description:
				'Upgraded legacy applications and addressed security issues reported by Veracode, improving maintainability and system integrity.'
		},
		{
			id: 3,
			role: 'Software Engineer',
			company: 'Leapfrog Technology',
			duration: 'Jan 2023 - Oct 2024',
			description:
				'Contributed to healthcare projects involving complex business logic for prescription processing workflows.'
		},
		{
			id: 4,
			role: 'Associate Software Engineer',
			company: 'Leapfrog Technology',
			duration: 'Jan 2022 - Dec 2022',
			description:
				'Contributed to drug discovery management project by creating custom web components and CRUD backend.'
		},
		{
			id: 5,
			role: 'Software Engineer Intern',
			company: 'Leapfrog Technology',
			duration: 'Oct 2021 - Dec 2021',
			description: 'Learned basics of web development and created browser based games.'
		}
	];

	const nextSection: string = 'education';
	const nextSectionlabel: string = 'Academic Lore';

	const scrollText: string = 'Scroll for academic trauma (and triumph) ↓';
</script>

<Section id="experience">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<ExperienceView {experiences} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
