<script>
	import '../app.css';
	import { page } from '$app/stores';
</script>

<svelte:head>
	<title>Waddup homies</title>
</svelte:head>
<nav class="w-full py-4 my-0 px-4 text-blue-500 bg-neutral-700">
	{#if !$page.data.user}
		<button
			class="bg-transparent hover:text-orange-400 text-orange-100 font-semibold py-2 px-4 hover:border-transparent rounded"
		>
			<a href="/login">Log In</a>
		</button>
		<button
			class="bg-transparent hover:text-orange-400 text-orange-100 font-semibold py-2 px-4 hover:border-transparent rounded"
		>
			<a href="/reg">Register</a>
		</button>
	{/if}

	{#if $page.data.user}
		<form
			action="/logout"
			method="POST"
		>
			<button
				class="bg-transparent hover:text-orange-400 text-orange-100 font-semibold hover:text-white py-2 px-4"
				type="submit">Log out</button
			>
		</form>
	{/if}
</nav>

<main class="flex justify-center">
	<slot />
</main>

<style lang="postcss">
	@import url('https://use.typekit.net/oql0hxn.css');
	:global(html) {
		background-color: #dfd3db;
		font-family: loos-wide, sans-serif;
	}
	form {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
