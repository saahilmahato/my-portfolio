<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ParagraphBlock from '$lib/components/ParagraphBlock.svelte';
	import ChipsBar from '$lib/components/ChipsBar.svelte';

	const headlineText: string = 'From Logic to Impact';

	const aboutText: Array<{ id: string; text: string }> = [
		{
			id: 'Foundations',
			text: `I'm a software engineer who thrives at the intersection of intuition and logic, where late-night prototypes collide with long-term systems thinking, I approach every build not just as a technical challenge but as an opportunity to create tools that are meaningful, functional and quietly elegant, my work is driven by a desire to bridge the gap between human insight and machine precision, because great software should feel less like a product and more like a conversation.`
		},
		{
			id: 'Execution',
			text: `From scrappy weekend experiments to deeply scoped platforms, I operate across the full stack and beyond the codebase, blending algorithmic rigor with product awareness, I believe the best engineers move between abstraction layers with ease, balancing clean architecture with fast iteration, always optimizing not just for performance but for clarity, for intent, for that sense of "Yes! This just makes sense."`
		},
		{
			id: 'Exploration',
			text: `I build in the spaces where ambiguity lives, where the path forward isn't obvious and the requirements are still evolving, because that's where the real magic happens, constraints become creative prompts, blockers become puzzle pieces, and deadlines become fuel, I'm not here to replicate what already exists, I'm here to invent responsibly, to experiment with discipline, and to push boundaries without losing the plot.`
		},
		{
			id: 'Craft',
			text: `My thinking is shaped by systems but never trapped by them, I move with the curiosity of a researcher, the momentum of a startup operator, and the craft of a product-minded engineer, I care about the edge cases, the silent failures, the latency that ruins delight, and the affordances that empower real people to do real things, I write code like I'm writing a story with structure, with rhythm, with voice.`
		},
		{
			id: 'Future',
			text: `In a world where AI is changing the definition of creativity and automation is rewriting the role of developers, I'm not just adapting to the shift, I'm designing for it, my goal isn't to just keep up, it's to set the pace, to explore the new frontiers of human-computer collaboration, and to make sure that as the tools evolve, the soul of the work remains grounded in purpose, in people, and in the quiet elegance of well-built systems.`
		}
	];

	const highlights: Array<object> = [
		{ id: 1, text: '📚 Relentlessly curious, never complacent' },
		{ id: 2, text: '⚡ Prototyping fast, scaling with intent' },
		{ id: 3, text: '🧩 Translating human intuition into machine logic' }
	];

	const nextSection: string = 'projects';
	const nextSectionlabel: string = 'Built This 💪';

	const scrollText: string = 'Built with caffeine, cursed bugs, and vibes ↓';
</script>

<Section id="about">
	<Headline text={headlineText} />
	{#each aboutText as paragraph (paragraph.id)}
		<ParagraphBlock text={paragraph.text} />
	{/each}
	<ChipsBar chips={highlights} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
