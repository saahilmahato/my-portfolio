<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import ProjectView from '$lib/components/ProjectView.svelte';

	const headlineText = 'Projects';
	const subHeadlineText =
		'Behold, my weird and wonderful projects. Roast them, remix them, fork them into another dimension. I welcome all feedback and unhinged contributions 🛠️✨';

	const projects = [
		{
			id: 1,
			title: 'OptiTraffic',
			description:
				'A simulation to test the performance of various traffic light control strategies.',
			status: 'Maintenance',
			techStack: 'Python, Pytorch, Pygame',
			duration: 'Aug 2024 - Feb 2025',
			features: ['Realtime traffic simulation', 'Adaptive traffic lights', 'Recordable Statistics'],
			tags: ['Simulation', 'AI'],
			link: 'https://github.com/saahilmahato/OptiTraffic',
			github: 'https://github.com/saahilmahato/OptiTraffic',
			label: 'Research Simulation'
		}
	];

	const nextSection = 'publications';
	const nextSectionlabel = 'The Research Files';

	const scrollText = 'Wanna read what kept me up at 3am? ↓';
</script>

<Section id="projects">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<ProjectView {projects} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
