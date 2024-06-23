<script lang="ts">
	import Plug from './Plug.svelte';
	let amt = $derived(Math.round(Math.random() * 3) || 1);
	const number = $derived(Array.from({ length: amt }));
</script>

{#if amt < 2}
	<div style=" --amt: {amt};">
		<Plug loft />
	</div>
{:else}
	<div style=" --amt: {amt};">
		{#each number as _p}
			<Plug loft={false} />
		{/each}
	</div>
{/if}

<style>
	div {
		display: grid;
		grid-template-columns: repeat(var(--amt), 1fr);
		gap: 2ex;
	}
</style>
