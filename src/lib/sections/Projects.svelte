<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import ProjectView from '$lib/components/ProjectView.svelte';

	const headlineText: string = 'Projects';
	const subHeadlineText: string =
		'Behold, my weird and wonderful projects. Remix them, fork them into another dimension. I welcome all feedback and unhinged contributions 🛠️✨';

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
			label: 'Research Project'
		},
		{
			id: 2,
			title: 'ATHENA',
			description:
				'ATHENA is a library designed to facilitate the creation of intelligent, dynamic NPCs',
			status: 'In Progress',
			techStack: 'Python, google-genai',
			duration: 'Mar 2025 - Presnt',
			features: [
				'Realistic dialogues',
				'Schema responses for game context',
				'Varying responses according to personality'
			],
			tags: ['Game', 'AI'],
			link: 'https://github.com/saahilmahato/ATHENA',
			github: 'https://github.com/saahilmahato/ATHENA',
			label: 'Library'
		},
		{
			id: 3,
			title: 'Melody Generator',
			description:
				'A research project that explores how midi files and transformers can be used to generate melodies',
			status: 'Maintenance',
			techStack: 'Python, Pytorch',
			duration: 'Jul 2024 - Sep 2024',
			features: [
				'Preprocessing of MIDI files',
				'Train transformers to generate note sequences',
				'Multiple instruments'
			],
			tags: ['GenAI', 'Music'],
			link: 'https://github.com/saahilmahato/MelodyGenerator',
			github: 'https://github.com/saahilmahato/MelodyGenerator',
			label: 'Research Project'
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
