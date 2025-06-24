<script lang="ts">
	let { experiences } = $props();

	const isCurrent = (duration: string) => {
		return duration.toLowerCase().includes('present');
	};
</script>

<div class="mx-auto mb-10 max-w-4xl space-y-6">
	<div class="relative">
		<div
			class="absolute top-0 bottom-0 left-8 w-0.5 bg-gradient-to-b from-emerald-400 via-green-500 to-teal-400 shadow-sm"
		></div>

		{#each experiences as experience (experience.id)}
			<div class="group relative mb-12 flex items-start">
				<div
					class="absolute left-6 z-10 h-4 w-4 rounded-full border-4 bg-gradient-to-br from-lime-100 to-white transition-all duration-300 group-hover:scale-125
					{isCurrent(experience.duration)
						? 'border-emerald-500 shadow-lg shadow-emerald-200'
						: 'border-green-400 group-hover:border-emerald-500'}"
				></div>

				<div class="ml-16 w-full">
					<div
						class="via-green-25 to-emerald-25 relative overflow-hidden rounded-xl border border-green-200 bg-gradient-to-br from-white p-6 shadow-lg
						backdrop-blur-sm transition-all duration-300 hover:-translate-y-1
						hover:border-emerald-300 hover:shadow-xl"
					>
						<div
							class="absolute inset-0 bg-gradient-to-br from-emerald-200 to-transparent opacity-5"
						></div>

						<div class="relative z-10">
							<div class="mb-2 flex flex-col sm:flex-row sm:items-center sm:justify-between">
								<h3 class="mb-1 text-xl font-semibold text-emerald-800 sm:mb-0">
									{experience.role}
								</h3>
								{#if isCurrent(experience.duration)}
									<span
										class="inline-flex items-center rounded-full border border-emerald-200 bg-gradient-to-r from-emerald-100 to-teal-100 px-3 py-1 text-xs font-medium text-emerald-700"
									>
										Current
									</span>
								{/if}
							</div>

							<div class="mb-3 flex items-center gap-2">
								<svg class="h-5 w-5 text-teal-600" fill="currentColor" viewBox="0 0 20 20">
									<path
										fill-rule="evenodd"
										d="M4 4a2 2 0 012-2h8a2 2 0 012 2v12a1 1 0 110 2h-3a1 1 0 01-1-1v-6a1 1 0 00-1-1H9a1 1 0 00-1 1v6a1 1 0 01-1 1H4a1 1 0 110-2V4zm3 1h2v2H7V5zm2 4H7v2h2V9zm2-4h2v2h-2V5zm2 4h-2v2h2V9z"
										clip-rule="evenodd"
									/>
								</svg>
								<span class="text-lg font-medium text-teal-700">{experience.company}</span>
							</div>

							<div class="mb-4 flex items-center gap-2">
								<svg class="h-5 w-5 text-emerald-600" fill="currentColor" viewBox="0 0 20 20">
									<path
										fill-rule="evenodd"
										d="M6 2a1 1 0 00-1 1v1H4a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-1V3a1 1 0 10-2 0v1H7V3a1 1 0 00-1-1zm0 5a1 1 0 000 2h8a1 1 0 100-2H6z"
										clip-rule="evenodd"
									/>
								</svg>
								<span class="text-sm font-medium text-emerald-700">{experience.duration}</span>
							</div>

							<p class="text-left leading-relaxed text-green-800">{experience.description}</p>
						</div>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}

	.group {
		transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
	}

	@keyframes breathe {
		0%,
		100% {
			transform: scale(1);
		}
		50% {
			transform: scale(1.05);
		}
	}

	:global(.border-emerald-500) {
		animation: breathe 3s ease-in-out infinite;
	}

	@keyframes fadeIn {
		from {
			opacity: 0;
			transform: translateY(-50%) scale(0);
		}
		to {
			opacity: 0.6;
			transform: translateY(-50%) scale(1);
		}
	}
</style>
