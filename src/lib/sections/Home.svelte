<script lang="ts">
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ChipsBar from '$lib/components/ChipsBar.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import ProfilePicture from '$lib/components/ProfilePicture.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import Section from '$lib/components/Section.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';

	const profileImage: string = 'profile.png';
	const headlineText: string = "Hi! I'm Saahil Mahato";
	const subHeadlineText: string =
		"Building tomorrow's technology with today's coffee and yesterday's sleep schedule.";

	const links: Array<object> = [
		{ id: 1, text: '🐙 GitHub', href: 'https://github.com/saahilmahato' },
		{ id: 2, text: '💼 LinkedIn', href: 'https://www.linkedin.com/in/saahil-mahato-6810ba171/' },
		{ id: 3, text: '🐦 X (Twitter)', href: 'https://x.com/saahilxmahato' }
	];

	const nextSection: string = 'projects';
	const nextSectionlabel: string = 'Built This 💪';

	const scrollText: string = "Built with caffeine, cursed bugs, and vibes ↓";
</script>

<Section id="home">
	<ProfilePicture src={profileImage} />
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<ChipsBar chips={links} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
