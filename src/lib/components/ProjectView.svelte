<script lang="ts">
	let { projects } = $props();
</script>

<div class="mx-auto mb-10 flex w-full max-w-4xl flex-wrap justify-center gap-6 space-y-6 py-8">
	{#each projects as project, index (project.id)}
		<article
			class="group relative w-full rounded-2xl border border-green-200/50
             bg-gradient-to-br from-green-50/80 via-emerald-50/60 to-teal-50/80 p-6
             backdrop-blur-sm transition-all duration-500 ease-out
             hover:-translate-y-1 hover:border-green-300/60 hover:bg-gradient-to-br
             hover:from-green-50 hover:via-emerald-50 hover:to-teal-50 hover:shadow-xl hover:shadow-green-100/50
             md:w-[calc(50%-0.75rem)] md:p-8"
			style="animation-delay: {index * 100}ms"
		>
			<!-- Top accent line -->
			<div
				class="absolute top-0 right-0 left-0 h-1 rounded-t-2xl bg-gradient-to-r from-green-400 via-emerald-400
                  to-teal-400 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
			></div>

			<!-- Project type/status badge -->
			<div class="mb-4 flex items-center gap-3">
				<span
					class="inline-flex items-center rounded-full bg-gradient-to-r from-green-500 to-emerald-500 px-3 py-1 text-xs
                     font-semibold tracking-wide text-white uppercase shadow-sm"
				>
					{project.label || 'Project'}
				</span>
				<div class="h-px flex-1 bg-gradient-to-r from-green-200 via-green-100 to-transparent"></div>
				{#if project.status}
					<span class="rounded-lg bg-green-100/70 px-2 py-1 text-sm font-medium text-green-700">
						{project.status}
					</span>
				{/if}
			</div>

			<!-- Title -->
			<h3
				class="mb-3 text-xl leading-tight font-bold text-green-900 transition-colors group-hover:text-green-700 md:text-2xl"
			>
				{#if project.link}
					<a
						href={project.link}
						target="_blank"
						rel="noopener noreferrer"
						class="relative inline-block transition-colors duration-300 after:absolute
                    after:bottom-0 after:left-0 after:h-0.5 after:w-0 after:bg-gradient-to-r
                    after:from-green-500 after:to-emerald-500 after:transition-all
                    after:duration-300 hover:text-green-600 hover:after:w-full"
					>
						{project.title}
					</a>
				{:else}
					{project.title}
				{/if}
			</h3>

			<!-- Tech Stack -->
			{#if project.techStack}
				<p class="mb-2 text-sm font-medium text-green-800 md:text-base">
					Built with: {project.techStack}
				</p>
			{/if}

			<!-- Duration/Timeline -->
			{#if project.duration}
				<p class="mb-3 text-sm text-green-600 italic md:text-base">
					{project.duration}
				</p>
			{/if}

			<!-- Description -->
			{#if project.description}
				<p class="mb-4 text-sm leading-relaxed text-gray-700 md:text-base">
					{project.description}
				</p>
			{/if}

			<!-- Key Features -->
			{#if project.features && project.features.length > 0}
				<div class="mb-4">
					<h4 class="mb-2 text-sm font-semibold text-green-800">Key Features:</h4>
					<ul class="space-y-1 text-sm text-gray-700">
						{#each project.features as feature (feature)}
							<li class="flex items-start gap-2">
								<svg
									class="mt-1 h-3 w-3 flex-shrink-0 text-green-500"
									fill="currentColor"
									viewBox="0 0 20 20"
								>
									<path
										fill-rule="evenodd"
										d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
										clip-rule="evenodd"
									/>
								</svg>
								{feature}
							</li>
						{/each}
					</ul>
				</div>
			{/if}

			<!-- Tags -->
			{#if project.tags && project.tags.length > 0}
				<div class="mb-6 flex flex-wrap gap-2">
					{#each project.tags as tag (tag)}
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
				{#if project.link}
					<a
						href={project.link}
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
								d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
							/>
						</svg>
						View Project
					</a>
				{/if}

				{#if project.github}
					<a
						href={project.github}
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full border border-green-200/60
                    bg-green-100/80 px-4 py-2 text-sm font-medium text-green-700
                    transition-all duration-200 hover:-translate-y-0.5
                    hover:border-green-300/60 hover:bg-green-200/80
                    focus:ring-2 focus:ring-green-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 20 20">
							<path
								fill-rule="evenodd"
								d="M10 0C4.477 0 0 4.484 0 10.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0110 4.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.203 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.942.359.31.678.921.678 1.856 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0020 10.017C20 4.484 15.522 0 10 0z"
								clip-rule="evenodd"
							/>
						</svg>
						Source Code
					</a>
				{/if}

				{#if project.demo}
					<a
						href={project.demo}
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
								d="M14.828 14.828a4 4 0 01-5.656 0M9 10h1m4 0h1m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
							/>
						</svg>
						Live Demo
					</a>
				{/if}

				{#if project.documentation}
					<a
						href={project.documentation}
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full border border-teal-200/60
                    bg-teal-100/80 px-4 py-2 text-sm font-medium text-teal-700
                    transition-all duration-200 hover:-translate-y-0.5
                    hover:border-teal-300/60 hover:bg-teal-200/80
                    focus:ring-2 focus:ring-teal-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
							/>
						</svg>
						Documentation
					</a>
				{/if}

				{#if project.npm}
					<a
						href={project.npm}
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full border border-red-200/60
                    bg-red-100/80 px-4 py-2 text-sm font-medium text-red-700
                    transition-all duration-200 hover:-translate-y-0.5
                    hover:border-red-300/60 hover:bg-red-200/80
                    focus:ring-2 focus:ring-red-400 focus:ring-offset-2 focus:outline-none"
					>
						<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 20 20">
							<path
								d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"
							/>
						</svg>
						NPM Package
					</a>
				{/if}
			</div>

			<!-- Decorative element -->
			<div
				class="absolute top-6 right-6 opacity-10 transition-opacity duration-300 group-hover:opacity-20"
			>
				<svg class="h-8 w-8 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"
					/>
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
