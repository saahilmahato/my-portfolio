<script>
	import About from '$lib/sections/About.svelte';
	import Home from '$lib/sections/Home.svelte';
	import NavBar from '$lib/sections/NavBar.svelte';
	import Projects from '$lib/sections/Projects.svelte';
	import Publications from '$lib/sections/Publications.svelte';
</script>

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
	</main>
</div>
