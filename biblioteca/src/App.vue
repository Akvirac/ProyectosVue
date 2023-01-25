<script setup>
import { ref } from 'vue'
import ButtonLive from './components/ButtonLive.vue'
import BookList from './components/BookList.vue'
import CreateBook from './components/CreateBook.vue'

//Variables, arrays, objetos.
const isFormActive = ref(false)
const books = ref([
	{
		bookName: 'harry potter y la camara secreta',
		author: 'JK. Rowling',
		price: '25',
		url: 'https://http2.mlstatic.com/D_NQ_NP_946078-MLA48084879386_112021-O.jpg',
		id: 1,
	},
	{
		bookName: 'harry potter y la camara secreta',
		author: 'JK. Rowling',
		price: '25',
		url: 'https://http2.mlstatic.com/D_NQ_NP_946078-MLA48084879386_112021-O.jpg',
		id: 2,
	},
	{
		bookName: 'harry potter y la camara secreta',
		author: 'JK. Rowling',
		price: '25',
		url: 'https://http2.mlstatic.com/D_NQ_NP_946078-MLA48084879386_112021-O.jpg',
		id: 3,
	},
])
const cart = ref([])
//Funcionalidades.
function submitBook(book) {
	books.value.push(book)
}
function buyBook(book) {
	console.log(book)
	const bookSelected = books.value.find((b) => b.id === book.id)
	books.value = books.value.filter((b) => b.id != book.id)
	cart.value.push(bookSelected)
}
</script>

<template>
	<div class="mt-5 h-screen place-items-center">
		<div class="flex justify-center">
			<ButtonLive
				class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2"
				@click="isFormActive = true"
				>Submit a new Book</ButtonLive
			>

			<ButtonLive
				class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2"
				@click="isFormActive = false"
				>Book List</ButtonLive
			>
		</div>
		<!-- {{ books }} -->
		<div class="flex justify-center mt-5">
			<CreateBook v-if="isFormActive" @submit="submitBook" />
			<BookList v-else :books="books" @buy="buyBook" />
		</div>
	</div>
</template>
