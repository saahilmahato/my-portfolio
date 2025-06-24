<script lang="ts">
	let { experiences } = $props();

	const isCurrent = (duration: string) => {
		return duration.toLowerCase().includes('present');
	};
</script>

<div
	class="via-emerald-25 mx-auto mb-8 max-w-4xl rounded-2xl bg-gradient-to-br from-green-50 to-teal-50 p-6"
>
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
								<span class="text-lg">🏢</span>
								<span class="text-lg font-medium text-teal-700">{experience.company}</span>
							</div>

							<div class="mb-4 flex items-center gap-2">
								<span class="text-lg">📅</span>
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
