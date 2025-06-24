<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import ExperienceView from '$lib/components/ExperienceView.svelte';

	const headlineText = 'Experience';
	const subHeadlineText = "Frontend? Backend? Infra? If it compiles (eventually), I'm in. 🦾";

	const experiences = [
		{
			id: 1,
			role: 'Software Engineer',
			company: 'Cedar Gate Technologies',
			duration: 'Dec 2024 - Present',
			description:
				'Currently upgrading a healthcare analytics platform with modern frameworks and resolving a large volume of security vulnerabilities to improve system integrity and compliance.'
		},
		{
			id: 2,
			role: 'Software Engineer',
			company: 'Leapfrog Technology',
			duration: 'Jan 2023 - Oct 2024',
			description:
				'Contributed to healthcare projects involving complex business logic for prescription processing workflows.'
		},
		{
			id: 3,
			role: 'Associate Software Engineer',
			company: 'Leapfrog Technology',
			duration: 'Jan 2022 - Dec 2022',
			description:
				'Contributed to drug discovery management project by creating custom web components and CRUD backend.'
		},
		{
			id: 4,
			role: 'Software Engineer Intern',
			company: 'Leapfrog Technology',
			duration: 'Oct 2021 - Dec 2021',
			description: 'Learned basics of web development and created browser based games.'
		}
	];

	const nextSection = 'education';
	const nextSectionlabel = 'Academic Lore';

	const scrollText = 'Scroll for academic trauma (and triumph) ↓';
</script>

<Section id="experience">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<ExperienceView {experiences} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
