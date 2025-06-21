<script>
	import CallToAction from '$lib/components/CallToAction.svelte';
	import ChipBar from '$lib/components/ChipBar.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import ProfilePicture from '$lib/components/ProfilePicture.svelte';
	import ScrollPrompt from '$lib/components/ScrollPrompt.svelte';
	import Section from '$lib/components/Section.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';

	const profileImage = 'profile.png';
	const headlineText = "I'm Saahil Mahato. I sudo the impossible";
	const subHeadlineText =
		"Building tomorrow's technology with today's coffee and yesterday's sleep schedule.";

	const tagLines = ['🧠 Reality Compiler', '🔍 Bug Archaeologist', '🦆 Rubber Duck Consultant'];

	const nextSection = 'about';
	const nextSectionlabel = 'Dive In';

	const scrollText = 'Scroll to Discover';
</script>

<Section id="home">
	<ProfilePicture src={profileImage} />
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />
	<ChipBar chips={tagLines} />
	<CallToAction section={nextSection} label={nextSectionlabel} />
	<ScrollPrompt text={scrollText} />
</Section>
