<script>
	let { children } = $props();
</script>

<div class="my-6 flex flex-wrap justify-center gap-6">
	{@render children()}
</div>
