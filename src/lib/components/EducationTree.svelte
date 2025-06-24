<script lang="ts">
	let { education } = $props();
</script>

<div class="via-emerald-25 mb-8 rounded-2xl bg-gradient-to-br from-green-50 to-lime-50 p-6">
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
						<span class="text-lg">🏫</span>
						<p class="text-lg">{edu.school}</p>
					</div>

					<div class="mb-3 flex items-center gap-2 text-green-600">
						<span class="text-lg">📅</span>
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
