<script lang="ts">
	import type { ActionData } from './$types';
	export let form: ActionData;
</script>

<div class="max-w-lg mx-auto flex-column">
	<h1 class="text-3xl text-white font-medium">Login</h1>
	<div class="max-w-md mx-auto flex p-6 justify-center">
		<form
			class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4"
			action="?/login"
			method="POST"
		>
			<div class="mb-4">
				<label for="username">Username</label>
				<input
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					id="username"
					name="username"
					type="text"
					required
				/>
			</div>
			<div class="mb-4">
				<label for="password">Password</label>
				<input
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					id="password"
					name="password"
					type="password"
					required
				/>
			</div>

			{#if form?.invalid}
				<p class="text-sm text-orange-600">
					Username and password is required.
				</p>
			{/if}

			{#if form?.credentials}
				<p class="text-sm text-orange-600 italic">
					You have entered the wrong credentials.
				</p>
			{/if}

			<div class="flex flex-col justify-center">
				<button
					class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline my-2 justify-center"
					type="submit">Login</button
				>
				<p class="text-xs my-2">Need to sign up?</p>
				<a
					class="text-2xl"
					href="/reg"
				>
					<button
						class="bg-amber-400 hover:bg-amber-500 text-white font-bold py-2 px-4 text-sm rounded focus:outline-none focus:shadow-outline"
					>
						Register
					</button>
				</a>
			</div>
		</form>
	</div>
</div>
