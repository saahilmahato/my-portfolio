<script>
	let menuOpen = false;

	const sections = [
		{ id: 'home', title: 'Home' },
		{ id: 'about', title: 'About' },
		{ id: 'projects', title: 'Projects' },
		{ id: 'publications', title: 'Publications' },
		{ id: 'experience', title: 'Experience' },
		{ id: 'education', title: 'Education' },
		{ id: 'contact', title: 'Contact' }
	];

	const toggleMenu = () => {
		menuOpen = !menuOpen;
	};
</script>

<nav
	class={`fixed top-0 left-0 z-50 w-full ${menuOpen ? 'border-b border-green-300 bg-green-200/60 shadow-sm backdrop-blur-md' : 'bg-transparent'} md:border-b md:border-green-300 md:shadow-sm md:backdrop-blur-md md:transition-all`}
>
	<div class="mx-auto max-w-screen-xl px-4">
		<div class="relative flex h-16 items-center justify-between">
			<!-- Desktop Nav -->
			<ul class="absolute left-1/2 hidden -translate-x-1/2 space-x-6 md:flex">
				{#each sections as section (section.id)}
					<li>
						<a
							href="#{section.id}"
							class="text-sm font-semibold text-green-900 transition hover:text-emerald-700"
						>
							{section.title}
						</a>
					</li>
				{/each}
			</ul>

			<!-- Hamburger (Mobile) -->
			<div class="ml-auto md:hidden">
				<button on:click={toggleMenu} aria-label="Toggle Menu">
					<svg class="h-6 w-6 text-green-900" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						/>
					</svg>
				</button>
			</div>
		</div>

		<!-- Mobile Dropdown -->
		{#if menuOpen}
			<ul class="flex flex-col space-y-3 py-4 md:hidden">
				{#each sections as section (section.id)}
					<li>
						<a
							href="#{section.id}"
							class="block text-center text-sm font-semibold text-green-900 transition hover:text-emerald-700"
							on:click={() => (menuOpen = false)}
						>
							{section.title}
						</a>
					</li>
				{/each}
			</ul>
		{/if}
	</div>
</nav>
