<script>
	let { chips } = $props();
</script>

<div class="mb-8 flex space-x-4">
	{#each chips as chip (chip)}
		<span class="rounded-full bg-white/30 px-4 py-2 font-medium text-green-800 backdrop-blur-sm">
			{chip}
		</span>
	{/each}
</div>
