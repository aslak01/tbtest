<script lang="ts">
	import Row from './Row.svelte';
	const rows = Array.from({ length: 10 });
</script>

<div class="page">
	{#each rows as _row}
		<Row />
	{/each}
</div>

<style>
	.page {
		display: flex;
		flex-direction: column;
	}
</style>
