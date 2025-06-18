<!-- components/home/Section.svelte -->
<script>
	let { id, children } = $props();
</script>

<section id={id} class="flex h-screen flex-col items-center justify-center bg-gradient-to-b from-green-100 via-green-200 to-green-50 px-6 text-center">
	{@render children()}
</section>
