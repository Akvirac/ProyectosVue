<script setup>
import ButtonLive from './ButtonLive.vue'
import { ref } from 'vue'
const book = ref({})
// function submitBook() {}
</script>

<template>
	<!-- {{ book }} Esto lo utilizamos para saber si esta cargando la informacion que nosotros queremos.-->
	<div
		class="max-w-md w-full bg-white border border-gray-200 rounded-lg shadow-md place-items-center p-4 space-y-4"
	>
		<h2 class="text-center py-4">New Book</h2>

		<label></label>

		<input
			type="text"
			placeholder="Book Name"
			class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
			v-model="book.bookName"
		/>

		<input
			type="text"
			placeholder="Autor"
			v-model="book.author"
			class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
		/>

		<input
			type="text"
			placeholder="Book price"
			v-model="book.price"
			class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
		/>

		<input
			type="text"
			placeholder="Img URL"
			v-model="book.url"
			class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
		/>

		<ButtonLive
			class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800 text-center"
			@click="$emit('submit', book)"
			>Submit</ButtonLive
		>
	</div>
</template>
