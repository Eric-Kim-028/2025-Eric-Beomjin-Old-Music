<script>
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="flex space-x-5 border-b p-2">
	<a href="/">Home</a>
	<a href="/favorites">Fav</a>
	<a href="/Artists">Artists</a>
	<a href="/user">Users</a>
	<a href="/Contact">Contact Us</a>
	<a href="/About">About</a>
</div>


{@render children?.()}
