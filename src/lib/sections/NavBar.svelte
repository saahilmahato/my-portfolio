<script>
	const sections = [
		{ id: 'home', title: 'Home' },
		{ id: 'about', title: 'About' },
		{ id: 'projects', title: 'Projects' },
		{ id: 'publications', title: 'Publications' },
		{ id: 'experience', title: 'Experience' },
		{ id: 'contact', title: 'Contact' }
	];
</script>

<nav class="fixed top-0 z-50 w-full bg-white/30 backdrop-blur-md">
	<ul class="flex justify-center space-x-8 py-4">
		{#each sections as section (section.id)}
			<li>
				<a href="#{section.id}" class="font-medium hover:text-green-700">
					{section.title}
				</a>
			</li>
		{/each}
	</ul>
</nav>
