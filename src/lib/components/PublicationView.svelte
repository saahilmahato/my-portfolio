<script lang="ts">
	let { publications } = $props();
</script>

<div class="mx-auto max-w-4xl space-y-6 py-8">
	{#each publications as publication, index (publication.title)}
		<article
			class="group relative rounded-2xl border border-green-200/50 bg-gradient-to-br
             from-green-50/80 via-emerald-50/60 to-teal-50/80 p-6 backdrop-blur-sm
             transition-all duration-500 ease-out hover:-translate-y-1
             hover:border-green-300/60 hover:bg-gradient-to-br hover:from-green-50
             hover:via-emerald-50 hover:to-teal-50 hover:shadow-xl hover:shadow-green-100/50 md:p-8"
			style="animation-delay: {index * 100}ms"
		>
			<!-- Top accent line -->
			<div
				class="absolute top-0 right-0 left-0 h-1 rounded-t-2xl bg-gradient-to-r from-green-400 via-emerald-400
                  to-teal-400 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
			></div>

			<!-- Publication type badge -->
			<div class="mb-4 flex items-center gap-3">
				<span
					class="inline-flex items-center rounded-full bg-gradient-to-r from-green-500 to-emerald-500 px-3 py-1 text-xs
                     font-semibold tracking-wide text-white uppercase shadow-sm"
				>
					{publication.label || 'Publication'}
				</span>
				<div class="h-px flex-1 bg-gradient-to-r from-green-200 via-green-100 to-transparent"></div>
				{#if publication.year}
					<span class="rounded-lg bg-green-100/70 px-2 py-1 text-sm font-medium text-green-700">
						{publication.year}
					</span>
				{/if}
			</div>

			<!-- Title -->
			<h3
				class="mb-3 text-xl leading-tight font-bold text-green-900 transition-colors group-hover:text-green-700 md:text-2xl"
			>
				{#if publication.link}
					<a
						href={publication.link}
						target="_blank"
						rel="noopener noreferrer"
						class="relative inline-block transition-colors duration-300 after:absolute
                    after:bottom-0 after:left-0 after:h-0.5 after:w-0 after:bg-gradient-to-r
                    after:from-green-500 after:to-emerald-500 after:transition-all
                    after:duration-300 hover:text-green-600 hover:after:w-full"
					>
						{publication.title}
					</a>
				{:else}
					{publication.title}
				{/if}
			</h3>

			<!-- Authors -->
			{#if publication.authors}
				<p class="mb-2 text-sm font-medium text-green-800 md:text-base">
					{publication.authors}
				</p>
			{/if}

			<!-- Venue -->
			{#if publication.venue}
				<p class="mb-3 text-sm text-green-600 italic md:text-base">
					{publication.venue}
				</p>
			{/if}

			<!-- Description -->
			{#if publication.description}
				<p class="mb-4 text-sm leading-relaxed text-gray-700 md:text-base">
					{publication.description}
				</p>
			{/if}

			<!-- Tags -->
			{#if publication.tags && publication.tags.length > 0}
				<div class="mb-6 flex flex-wrap gap-2">
					{#each publication.tags as tag (tag)}
						<span
							class="inline-flex items-center rounded-full border border-emerald-200/50 bg-emerald-100/80 px-2.5
                         py-1 text-xs font-medium text-emerald-800
                         transition-all duration-200 hover:-translate-y-0.5 hover:bg-emerald-200/80"
						>
							#{tag}
						</span>
					{/each}
				</div>
			{/if}

			<!-- Action Links -->
			<div class="flex flex-wrap gap-3">
				{#if publication.link}
					<a
						href={publication.link}
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex transform items-center gap-2 rounded-full bg-gradient-to-r
                    from-green-500 to-emerald-500 px-4 py-2 text-sm font-semibold
                    text-white shadow-md transition-all duration-200
                    hover:-translate-y-0.5 hover:from-green-600 hover:to-emerald-600 hover:shadow-lg
                    focus:ring-2 focus:ring-green-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
							/>
						</svg>
						Read Paper
					</a>
				{/if}

				{#if publication.doi}
					<a
						href="https://doi.org/{publication.doi}"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full border border-green-200/60
                    bg-green-100/80 px-4 py-2 text-sm font-medium text-green-700
                    transition-all duration-200 hover:-translate-y-0.5
                    hover:border-green-300/60 hover:bg-green-200/80
                    focus:ring-2 focus:ring-green-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1"
							/>
						</svg>
						DOI
					</a>
				{/if}

				{#if publication.arxiv}
					<a
						href="https://arxiv.org/abs/{publication.arxiv}"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full border border-emerald-200/60
                    bg-emerald-100/80 px-4 py-2 text-sm font-medium text-emerald-700
                    transition-all duration-200 hover:-translate-y-0.5
                    hover:border-emerald-300/60 hover:bg-emerald-200/80
                    focus:ring-2 focus:ring-emerald-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
							/>
						</svg>
						arXiv
					</a>
				{/if}

				{#if publication.github}
					<a
						href={publication.github}
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full border border-teal-200/60
                    bg-teal-100/80 px-4 py-2 text-sm font-medium text-teal-700
                    transition-all duration-200 hover:-translate-y-0.5
                    hover:border-teal-300/60 hover:bg-teal-200/80
                    focus:ring-2 focus:ring-teal-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 20 20">
							<path
								fill-rule="evenodd"
								d="M10 0C4.477 0 0 4.484 0 10.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0110 4.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.203 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.942.359.31.678.921.678 1.856 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0020 10.017C20 4.484 15.522 0 10 0z"
								clip-rule="evenodd"
							/>
						</svg>
						Code
					</a>
				{/if}
			</div>

			<!-- Decorative element -->
			<div
				class="absolute top-6 right-6 opacity-10 transition-opacity duration-300 group-hover:opacity-20"
			>
				<svg class="h-8 w-8 text-green-400" fill="currentColor" viewBox="0 0 20 20">
					<path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
				</svg>
			</div>
		</article>
	{/each}
</div>

<style>
	article {
		animation: fadeInUp 0.6s ease-out both;
	}

	@keyframes fadeInUp {
		from {
			opacity: 0;
			transform: translateY(30px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
</style>
