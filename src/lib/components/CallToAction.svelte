<script>
    let { section, label } = $props();
</script>

<a
	href={`#${section}`}
	class="rounded-full border-2 border-green-600 px-6 py-3 text-green-600 transition hover:bg-green-600 hover:text-white"
>
	{label}
</a>
