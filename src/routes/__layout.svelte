<script lang="ts">
	import Nav from '$lib/nav.svelte';
	import '../styles/style.css';
</script>

<Nav />
<main class="s">
	<slot />
</main>

<footer>
	<p>
		<a href="https://kit.svelte.dev">kit..dev</a>
	</p>
</footer>

<style>
	.s {
		background-color: blue;
	}
</style>
