<script>
	import '../app.css';
	import { page } from '$app/stores';
</script>

<svelte:head>
	<title>Waddup homies</title>
</svelte:head>
<nav>
	{#if !$page.data.user}
		<a href="/login">Log In</a>
		<a href="/reg">Register</a>
	{/if}

	{#if $page.data.user}
		<form
			action="/logout"
			method="POST"
		>
			<button type="submit">Log out</button>
		</form>
	{/if}
</nav>

<main>
	<slot />
</main>

<style lang="postcss">
	@import url('https://use.typekit.net/oql0hxn.css');
	:global(html) {
		background-color: theme(colors.gray.500);
		font-family: loos-wide, sans-serif;
	}
	form {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
