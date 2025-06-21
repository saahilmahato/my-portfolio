<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CardView from '$lib/components/CardView.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import Card from '$lib/components/Card.svelte';

	const headlineText = 'Publications';
	const subHeadlineText =
		"These are my published papers. Read 'em, cite 'em, challenge 'em. Academia needs a little disruption. 🧠⚡";

	const publications = [
		{
			title:
				'Multi-agent Reinforcement Learning vs. Fixed-Time Control for Traffic Signal Optimization: A Simulation Study',
			description: 'A statistical analysis of how MARL performs against Fixed time Traffic lights.',
			link: 'https://doi.org/10.48550/arXiv.2505.14544',
			label: 'Read Paper'
		}
	];

	const nextSection = 'experience';
	const nextSectionlabel = 'My Experience';

	const scrollText = 'See my experience';
</script>

<Section id="publications">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<CardView>
		{#each publications as item (item.title)}
			<Card title={item.title} description={item.description} link={item.link} label={item.label} />
		{/each}
	</CardView>
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
