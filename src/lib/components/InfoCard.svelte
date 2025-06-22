<script>
	let { title, institution, duration, description } = $props();
</script>

<div
	class="w-full max-w-md rounded-2xl bg-white p-6 shadow-xl transition-transform hover:scale-[1.02] hover:shadow-2xl"
>
	<h2 class="mb-1 text-xl font-semibold text-gray-900">{title}</h2>
	<p class="mb-1 font-medium text-green-600">{institution}</p>
	<p class="mb-4 text-sm text-gray-500 italic">{duration}</p>
	<p class="text-gray-700">{description}</p>
</div>
