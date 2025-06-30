<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import ProjectView from '$lib/components/ProjectView.svelte';

	const headlineText: string = 'Projects';
	const subHeadlineText: string =
		'Behold, my weird and wonderful projects. Roast them, remix them, fork them into another dimension. I welcome all feedback and unhinged contributions 🛠️✨';

	const projects: Array<object> = [
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
		},
		{
			id: 2,
			title: 'ATHENA',
			description:
				'ATHENA is a library designed to facilitate the creation of intelligent, dynamic NPCs',
			status: 'In Progress',
			techStack: 'Python, google-genai',
			duration: 'Mar 2025 - Presnt',
			features: ['Realistic dialogues', 'Schema responses for game context', 'Varying responses according to personality'],
			tags: ['Game', 'AI'],
			link: 'https://github.com/saahilmahato/ATHENA',
			github: 'https://github.com/saahilmahato/ATHENA',
			label: 'Library'
		}
	];

	const nextSection: string = 'publications';
	const nextSectionlabel: string = 'The Research Files';

	const scrollText: string = 'Wanna read what kept me up at 3am? ↓';
</script>

<Section id="projects">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<ProjectView {projects} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
