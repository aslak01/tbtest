<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();

	import '@fontsource-variable/inter';
</script>

<main>
	{@render children()}
</main>

<style>
	main {
		font-family: 'Inter Variable', sans-serif;
	}
</style>
