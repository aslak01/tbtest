<script lang="ts">
	let { loft = false }: { loft: boolean } = $props();
	import Title from './Title.svelte';
	import RandomImg from './RandomImg.svelte';
	import { headsOrTails } from '$lib/utils';
	let fiftyfifty = $state(headsOrTails());
	const str1 = 'This is a headline without spans';
	const str2 = '<span>A headline</span> <span>with spans</span>';
</script>

<div class="plug" class:loft>
	<RandomImg />
	<Title>
		{#if fiftyfifty}
			{@html str1}
		{:else}
			{@html str2}
		{/if}
	</Title>
</div>

<style>
	.plug {
		display: grid;
		max-height: 100%;
		gap: 1ex;
		grid-template-rows: 1fr 1fr;
	}
	.loft {
		grid-template-columns: 1fr 2fr;
	}
</style>
