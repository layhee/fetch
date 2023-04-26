<script lang="ts">
	import type { ActionData } from './$types';
	export let form: ActionData;
</script>

<div class="max-w-lg mx-auto flex-column">
	<h1 class="text-6xl my-4 text-blue-600 font-medium text-center">
		Join the club!
	</h1>
	<div class="max-w-md mx-auto flex justify-center p-6">
		<form
			class="bg-white rounded px-8 pt-6 pb-8 mb-4"
			method="POST"
			action="?/reg"
		>
			<div class="mb-4">
				<label for="username">Username</label>
				<input
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					type="text"
					required
					name="username"
					id="username"
				/>
			</div>
			<div class="mb-4">
				<label for="password">Password</label>
				<input
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					type="text"
					required
					name="password"
					id="password"
				/>
			</div>

			{#if form?.user}
				<p class="text-sm text-orange-600">Username is taken.</p>
			{/if}

			<div class="flex flex-col justify-center">
				<button
					class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline my-2 justify-center"
					type="submit">Register</button
				>
				<p class="text-xs my-2">Already a member?</p>
				<a
					class="text-2xl"
					href="/login"
				>
					<button
						class="bg-amber-400 hover:bg-amber-500 text-white font-bold py-2 px-4 text-sm rounded focus:outline-none focus:shadow-outline"
					>
						Log In
					</button>
				</a>
			</div>
		</form>
	</div>
</div>
