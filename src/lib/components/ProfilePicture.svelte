<script lang="ts">
	let { src } = $props();
</script>

<div class="mb-8">
	<div
		class="flex h-64 w-64 items-center justify-center rounded-full border-4 border-green-600 bg-white/50 backdrop-blur-sm"
	>
		<img {src} class="h-full w-full rounded-full object-cover" alt="Profile" />
	</div>
</div>
