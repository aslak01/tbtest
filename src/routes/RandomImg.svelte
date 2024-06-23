<script lang="ts">
	import { browser } from '$app/environment';

	const img = $derived.by(() => {
		const obj = import.meta.glob('$lib/assets/imgs/*', {
			import: 'default',
			eager: true
		});
		const imgs = Object.keys(obj);
		const imgIndex = Math.round(Math.random() * 10 * (Math.random() > 0.5 ? 2 : 1));
		return imgs[imgIndex];
	});
</script>

{#if browser}
	<img src={img} alt="bilde" />
{/if}

<style>
	img {
		max-width: 100%;
		min-width: 100%;
		height: 100%;
		max-height: 300px;
		object-fit: cover;
	}
</style>
