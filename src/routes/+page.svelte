<script lang="ts">
	import About from '$lib/sections/About.svelte';
	import Contact from '$lib/sections/Contact.svelte';
	import Education from '$lib/sections/Education.svelte';
	import Experience from '$lib/sections/Experience.svelte';
	import Home from '$lib/sections/Home.svelte';
	import NavBar from '$lib/sections/NavBar.svelte';
	import Projects from '$lib/sections/Projects.svelte';
	import Publications from '$lib/sections/Publications.svelte';
</script>

<svelte:head>
	<title>Saahil Mahato</title>
	<meta
		name="description"
		content="Portfolio of Saahil Mahato - Software Engineer, AI Engineer and Researcher"
	/>
	<meta name="keywords" content="Saahil Mahato, AI, Software, Portfolio" />
	<meta property="og:title" content="Saahil Mahato - Portfolio" />
	<meta
		property="og:description"
		content="Explore my projects, research, and engineering journey."
	/>
	<meta property="og:url" content="https://saahilmahato.pages.dev/" />
	<meta property="og:type" content="website" />
	<meta name="robots" content="index, follow" />
	<meta name="google-site-verification" content="VUz20qVVW2vUAJzBGnue2XoijmJfqWGmArAuFGp8TYc" />
</svelte:head>

<div
	class="min-h-screen bg-gradient-to-b from-green-100 via-green-200 to-green-50 font-sans text-gray-900"
>
	<header>
		<NavBar />
	</header>

	<main>
		<Home />
		<About />
		<Projects />
		<Publications />
		<Experience />
		<Education />
		<Contact />
	</main>
</div>
