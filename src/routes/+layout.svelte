<script>
	import '../app.css';
</script>

<slot />

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
