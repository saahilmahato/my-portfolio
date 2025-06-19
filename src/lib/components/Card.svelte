<script>
	let { title, description, link, label } = $props();
</script>

<div
	class="w-full max-w-md rounded-2xl bg-white p-6 shadow-xl transition-transform hover:scale-[1.02] hover:shadow-2xl"
>
	<h2 class="mb-2 text-2xl font-semibold text-gray-900">{title}</h2>
	<p class="mb-4 text-gray-700">{description}</p>
	<a
		href={link}
		target="_blank"
		rel="noopener noreferrer"
		class="inline-block rounded-full bg-gradient-to-r from-green-400 to-green-600 px-4 py-2 font-medium text-white transition hover:from-green-500 hover:to-green-700"
	>
		{label}
	</a>
</div>
