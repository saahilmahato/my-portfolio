<script>
	import Chip from './Chip.svelte';

	let { chips } = $props();
</script>

<div class="mb-8 flex flex-col space-y-2 sm:flex-row sm:space-y-0 sm:space-x-4">
	{#each chips as chip (chip)}
		<Chip text={chip} />
	{/each}
</div>
