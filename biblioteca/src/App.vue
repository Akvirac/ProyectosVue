<script setup>
//Todos mis import
import ButtonLive from './components/ButtonLive.vue'
import CreateBook from './components/CreateBook'
import BookList from './components/BookList.vue'
import { ref } from 'vue'
//Variables, arrays, objetos.
const isFormActive = ref(false)
const books = ref([])
//Funcionalidades.
function submitBook(book) {
	console.log(book)
	books.value.push(book)
}
</script>

<template>
	<div class="grid h-screen place-items-center">
		<ButtonLive
			class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
			@click="isFormActive = !isFormActive"
			>Submit a new Book</ButtonLive
		>
		<ButtonLive
			class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
			>Buy Book</ButtonLive
		>
		<ButtonLive
			class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
			>Book List</ButtonLive
		>
		{{ books }}

		<CreateBook v-if="isFormActive" @submit="submitBook" />
		<BookList v-else />
	</div>
</template>
