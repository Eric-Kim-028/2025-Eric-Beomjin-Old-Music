<script>
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="navbar bg-primary text-primary-content shadow-sm">
	<div class="flex-1">
		<a href="/" class="btn text-xl btn-ghost">Music8090</a>
	</div>
	<div class="flex-none">
		<ul class="menu menu-horizontal px-1">
			<li><a href="/favorites">Favorites</a></li>
			<li><a href="/votes">Votes</a></li>
		</ul>
	</div>
</div>

{@render children?.()}
