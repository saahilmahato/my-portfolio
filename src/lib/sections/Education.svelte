<script>
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import EducationTree from '$lib/components/EducationTree.svelte';

	const headlineText = 'Education';
	const SubheadlineText = 'Degrees acquired. Sanity mostly intact 🎓';

	const education = [
		{
			id: 1,
			degree: 'M.S in Advanced Computer Science',
			school: 'Keele University',
			duration: '2024 - 2025',
			description:
				'Dove deep into AI and software engineering. Wrapped it all up with a spicy multi-agent reinforcement learning thesis that taught traffic lights how to think.'
		},
		{
			id: 2,
			degree: 'B.S in Computer Science',
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

	<EducationTree {education} />

	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
