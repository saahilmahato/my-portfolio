<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CardView from '$lib/components/CardView.svelte';

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
</script>

<Section id="publications">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<CardView items={publications} />
</Section>
