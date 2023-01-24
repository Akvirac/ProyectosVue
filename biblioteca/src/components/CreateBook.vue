<script setup>
import ButtonLive from './ButtonLive.vue'
const newBook = {}
</script>

<template>
	<!-- {{ book }} -->
	<div
		class="max-w-lg bg-white border border-gray-200 rounded-lg w-full shadow-md place-items-center p-5 space-y-3"
	>
		<h2 class="text-center">New Book</h2>

		<label></label>
		<div>
			<input
				type="text"
				placeholder="Book Name"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
				v-model="newBook.bookName"
			/>
		</div>
		<div>
			<input
				type="text"
				placeholder="Autor"
				v-model="newBook.author"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
			/>
		</div>
		<div>
			<input
				type="text"
				placeholder="Book price"
				v-model="newBook.price"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
			/>
		</div>
		<div>
			<input
				type="text"
				placeholder="Img URL"
				v-model="newBook.url"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
			/>
		</div>
		<div class="flex justify-center">
			<ButtonLive
				class="inline focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mb-2"
				@click="$emit('submit', newBook)"
				>Submit</ButtonLive
			>
		</div>
	</div>
</template>
