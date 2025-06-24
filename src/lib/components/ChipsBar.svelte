<script lang="ts">
	let { chips } = $props();
</script>

<div class="mb-16 flex flex-wrap gap-2">
	{#each chips as chip (chip.id)}
		{#if chip.href}
			<a
				href={chip.href}
				target="_blank"
				rel="noopener noreferrer"
				class="inline-flex cursor-pointer items-center rounded-full border
                   border-green-200/60 bg-green-100/80 px-3 py-1.5 text-sm font-medium
                   text-green-700 transition-all duration-200
                   hover:-translate-y-0.5 hover:border-green-300/60 hover:bg-green-200/80
                   hover:shadow-md focus:ring-2 focus:ring-green-400 focus:ring-offset-2
                   focus:outline-none"
			>
				{chip.text}
				<svg class="ml-1 h-3 w-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
					/>
				</svg>
			</a>
		{:else}
			<span
				class="inline-flex items-center rounded-full border border-gray-200/60
                   bg-green-100/80 px-3 py-1.5 text-sm font-medium text-gray-700"
			>
				{chip.text}
			</span>
		{/if}
	{/each}
</div>
