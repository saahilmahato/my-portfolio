<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import EducationView from '$lib/components/EducationView.svelte';

	const headlineText: string = 'Education';
	const SubheadlineText: string = 'Degrees acquired. Sanity mostly intact 🎓';

	const education: Array<object> = [
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

	const nextSection: string = 'contact';
	const nextSectionlabel: string = 'Send a Message';

	const scrollText: string = 'Have questions? Or compliments? I accept both. ↓';
</script>

<Section id="education">
	<Headline text={headlineText} />
	<Subheadline text={SubheadlineText} />
	<EducationView {education} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
