<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import InfoCard from '$lib/components/InfoCard.svelte';
	import CardView from '$lib/components/CardView.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';

	const headlineText = 'Education';
	const SubheadlineText = 'Degrees acquired. Sanity mostly intact 🎓';

	const education = [
		{
			degree: 'M.Sc. in Advanced Computer Science',
			school: 'Keele University',
			duration: '2024 - 2025',
			description:
				'Dove deep into AI and software engineering. Wrapped it all up with a spicy multi-agent reinforcement learning thesis that taught traffic lights how to think.'
		},
		{
			degree: 'B.Sc. in Computer Science',
			school: 'Kathmandu University',
			duration: '2017 - 2022',
			description:
				'Got the fundamentals down — algorithms, OS, networks, databases, and a lot of caffeine-fueled late nights. Classic CS core with bonus chaos.'
		}
	];

	const nextSection = 'contact';
	const nextSectionlabel = 'Send a Message';

	const scrollText = 'Have questions? Or compliments? I accept both. ↓';
</script>

<Section id="education">
	<Headline text={headlineText} />
	<Subheadline text={SubheadlineText} />

	<CardView>
		{#each education as edu (edu.degree)}
			<InfoCard
				title={edu.degree}
				institution={edu.school}
				duration={edu.duration}
				description={edu.description}
			/>
		{/each}
	</CardView>
	
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
