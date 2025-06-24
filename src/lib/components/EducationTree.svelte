<script lang="ts">
	let { education } = $props();
</script>

<div class="mb-8">
	<div class="mx-auto max-w-4xl">
		<div class="grid gap-8 md:grid-cols-2">
			{#each education as edu (edu.id)}
				<div
					class="animate-fade-in transform rounded-xl border border-green-200 bg-gradient-to-br from-white to-green-50 p-6 shadow-md transition duration-300 ease-in-out hover:scale-[1.02] hover:border-emerald-300 hover:shadow-xl hover:shadow-emerald-200/50"
				>
					<div class="mb-3 flex items-center gap-3 text-emerald-800">
						<span class="animate-bounce-slow text-2xl">🎓</span>
						<h3 class="text-xl font-semibold">{edu.degree}</h3>
					</div>

					<div class="mb-2 flex items-center gap-3 text-teal-700">
						<svg class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20">
							<path
								d="M10.394 2.08a1 1 0 00-.788 0l-7 3a1 1 0 000 1.84L5.25 8.051a.999.999 0 01.356-.257l4-1.714a1 1 0 11.788 1.838L7.667 9.088l1.94.831a1 1 0 00.787 0l7-3a1 1 0 000-1.838l-7-3zM3.31 9.397L5 10.12v4.102a8.969 8.969 0 00-1.05-.174 1 1 0 01-.89-.89 11.115 11.115 0 01.25-3.762zM9.3 16.573A9.026 9.026 0 007 14.935v-3.957l1.818.78a3 3 0 002.364 0l5.508-2.361a11.026 11.026 0 01.25 3.762 1 1 0 01-.89.89 8.968 8.968 0 00-5.694 2.566 1 1 0 01-1.066-.042z"
							/>
						</svg>
						<p class="text-lg">{edu.school}</p>
					</div>

					<div class="mb-3 flex items-center gap-2 text-green-600">
						<svg class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20">
							<path
								fill-rule="evenodd"
								d="M6 2a1 1 0 00-1 1v1H4a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-1V3a1 1 0 10-2 0v1H7V3a1 1 0 00-1-1zm0 5a1 1 0 000 2h8a1 1 0 100-2H6z"
								clip-rule="evenodd"
							/>
						</svg>
						<p class="text-sm font-medium">{edu.duration}</p>
					</div>

					<p class="text-left leading-relaxed text-green-800">{edu.description}</p>
				</div>
			{/each}
		</div>
	</div>
</div>

<style>
	@keyframes fade-in {
		from {
			opacity: 0;
			transform: translateY(20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
	.animate-fade-in {
		animation: fade-in 0.6s ease-out;
	}

	@keyframes bounce-slow {
		0%,
		100% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(-4px);
		}
	}
	.animate-bounce-slow {
		animation: bounce-slow 2.5s infinite;
	}
</style>
