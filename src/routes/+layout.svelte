<script>
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="menu">
	<a href="/">Home</a>
	<a href="/about">About</a>
</div>

{@render children?.()}

<style>
	.menu {
		background-color: lightgray;
		padding: 10px;
	}
</style>