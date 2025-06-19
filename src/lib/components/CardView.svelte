<script>
	import Card from './Card.svelte';

	let { items } = $props();
</script>

<div class="my-6 grid gap-6 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
	{#each items as item (item.title)}
		<Card title={item.title} description={item.description} link={item.link} label={item.label} />
	{/each}
</div>
