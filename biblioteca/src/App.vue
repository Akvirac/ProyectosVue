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

<template class="">
	<div
		class="flex flex-col space-y-6 mt-10 items-center justify-center place-items-center"
	>
		<div class="flex space-between">
			<div>
				<ButtonLive
					class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
					:class="[isFormActive && 'opacity-50']"
					@click="isFormActive = true"
					>Submit a new Book</ButtonLive
				>
			</div>

			<div>
				<ButtonLive
					class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
					:class="[!isFormActive && 'opacity-50']"
					@click="isFormActive = false"
					>Book List</ButtonLive
				>
			</div>
			<div>
				<ButtonLive
					class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
					>Buy Book</ButtonLive
				>
			</div>
		</div>
		<!-- {{ books }} chequeamos que esta recibiendo la informacion del hijo. -->

		<CreateBook v-if="isFormActive" @submit="submitBook" />
		<BookList v-else :books="books" />
	</div>
</template>
