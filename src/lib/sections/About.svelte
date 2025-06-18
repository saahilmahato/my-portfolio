<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import ChipBar from '$lib/components/ChipBar.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ParagraphBlock from '$lib/components/ParagraphBlock.svelte';

	const headlineText = 'More than Code';

	const aboutText = `
		I'm a software engineer who enjoys turning caffeine and chaos into clean code. 
		Whether it's a scrappy weekend project or a long-term moonshot, I focus on building tools and experiences 
		that actually matter.
		My toolkit spans from low-level logic to high-level product thinking, because shipping great tech 
		requires more than just syntax. I thrive in the space between creative exploration and structured execution.
	`;

	const highlights = [
		'🧠 Always learning, never settling',
		'🚀 From quick hacks to long-haul visions',
		'🌍 Bridging human needs with machine logic'
	];

	const nextSection = 'projects';
	const nextSectionlabel = 'See My Work';

	const scrollText = 'Explore my Projects';
</script>

<Section id="about">
	<Headline text={headlineText} />
	<ParagraphBlock text={aboutText} />
	<ChipBar chips={highlights} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
