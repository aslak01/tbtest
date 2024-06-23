<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<article>
	<!-- svelte-ignore a11y_invalid_attribute -->
	<a href="#">
		<h2>
			{@render children()}
		</h2>
	</a>
</article>

<style>
	/* article { */
	/* 	max-width: 480px; */
	/* } */
	a {
		text-decoration: none;
	}
	a:hover {
		text-decoration: underline;
	}
	a,
	a:hover {
		color: unset;
	}
	h2 {
		margin: 0;
		font-size: 6ch;
		font-weight: 900;
		hyphens: auto;
		-webkit-hyphens: auto;
		line-height: 1;
	}
</style>
