<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import CardView from '$lib/components/CardView.svelte';

	const headlineText = 'Projects';
	const subHeadlineText =
		'Behold, my weird and wonderful projects. Roast them, remix them, fork them into another dimension. I welcome all feedback and unhinged contributions 🛠️✨';

	const projects = [
		{
			title: 'OptiTraffic',
			description:
				'A simulation to test the performance of various traffic light control strategies.',
			link: 'https://github.com/codesaahil/OptiTraffic',
			label: 'View Project'
		}
	];

	const nextSection = 'publications';
	const nextSectionlabel = 'Publications';

	const scrollText = 'Read my papers';
</script>

<Section id="projects">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<CardView items={projects} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
