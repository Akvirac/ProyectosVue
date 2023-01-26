<script setup>
import Button from './Button.vue'
</script>
<template>
	<div class="pt-8">
		<div
			class="justify-center card max-w-sm bg-white border border-gray-200 rounded-lg shadow-md shadow p-3 text-center md:text-base text-sm bg-cyan-300"
		>
			<label><h2 class="font-semibold">User Name</h2> </label>
			<input class="border-solid border-2 rounded-md" />
			<label><h2 class="font-semibold">Password</h2> </label>
			<input type="password" class="border-solid border-2 rounded-md" />
			<div class="justify-center pt-4">
				<Button
					class="border-solid border-2 rounded-md font-semibold px-2 py-2 bg-sky-500 shadow-md shadow"
				>
					Login
				</Button>
			</div>
		</div>
	</div>
</template>
