<script lang="ts">
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

{#if img}
	<img src={img} alt="ill" />
{/if}

<style>
	img {
		max-width: 100%;
	}
</style>
