<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import PublicationView from '$lib/components/PublicationView.svelte';

	const headlineText: string = 'Publications';
	const subHeadlineText: string =
		"These are my published papers. Read 'em, cite 'em, challenge 'em. Academia needs a little disruption. 🧠⚡";

	const publications: Array<object> = [
		{
			id: 1,
			title: 'Smart Traffic Signals: Comparing MARL and Fixed-Time Strategies',
			authors: 'Saahil Mahato',
			year: '2025',
			description: 'A statistical analysis of how MARL performs against Fixed time Traffic lights.',
			tags: ['AI', 'ML', 'MARL', 'Traffic lights', 'Traffic Optimization'],
			label: 'Preprint',
			link: 'https://arxiv.org/pdf/2505.14544',
			arxiv: '2505.14544',
			doi: '10.48550/arXiv.2505.14544',
			github: 'https://github.com/saahilmahato/OptiTraffic'
		}
	];

	const nextSection: string = 'experience';
	const nextSectionlabel: string = 'Experience Unlocked';

	const scrollText: string = "Spoiler: I didn't just vibe, I shipped. ↓";
</script>

<Section id="publications">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<PublicationView {publications} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
