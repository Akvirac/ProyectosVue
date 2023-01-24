<script setup>
import { ref } from 'vue'

import Button from './components/Button.vue'
import BookList from './components/BookList.vue'
import CreateBook from './components/CreateBook.vue'
import BooksCart from './components/BooksCart.vue'

//Variables, arrays, objetos.
//La variable para cambiar entre tabs.
const isFormActive = ref(2)
// Objeto donde almacenamos todos los libros.
const books = ref([
	{
		bookName: 'Harry Potter y la camara secreta',
		author: 'JK. Rowling',
		price: '25',
		url: 'https://http2.mlstatic.com/D_NQ_NP_946078-MLA48084879386_112021-O.jpg',
		id: 1,
	},
	{
		bookName: 'Harry Potter y el prisionero de Azkaban',
		author: 'JK. Rowling',
		price: '25',
		url: 'https://contentv2.tap-commerce.com/cover/large/9789878000121_1.jpg?id_com=1113',
		id: 2,
	},
	{
		bookName: 'Harry Potter y el caliz de fuego',
		author: 'JK. Rowling',
		price: '25',
		url: 'https://contentv2.tap-commerce.com/cover/large/9788418174599_1.jpg?id_com=1113',
		id: 3,
	},
])
//Objeto donde vemos el carrito.
const cart = ref([])
//Variable para contador del carro.
// const nCart = 0
//Funcionalidades.
let idNum = 3
function submitBook(book) {
	idNum = idNum + 1
	book.id = idNum
	books.value.push(book)

	// books.value..push(idNum)
	// console.log(idNum)
	// console.log(books)
}
function buyBook(book) {
	console.log(book)
	const bookSelected = books.value.find((b) => b.id === book.id)
	books.value = books.value.filter((b) => b.id != book.id)
	cart.value.push(bookSelected)
}
function returnBook(book) {
	console.log(book)
	const bookSelected = cart.value.find((b) => b.id === book.id)
	cart.value = cart.value.filter((b) => b.id != book.id)
	books.value.push(bookSelected)
}
</script>

<template>
	<div class="mt-5 h-screen place-items-center">
		<div class="flex justify-center">
			<Button
				class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
				@click="isFormActive = 1"
				>Submit a new Book</Button
			>

			<Button
				class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
				@click="isFormActive = 2"
				>Book List</Button
			>
			<Button
				class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
				@click="isFormActive = 3"
			>
				Cart
			</Button>
		</div>
		<!-- {{ books }} -->
		<div class="flex justify-center mt-5">
			<CreateBook v-if="isFormActive === 1" @submit="submitBook" />
			<BookList v-if="isFormActive === 2" :books="books" @buy="buyBook" />
			<BooksCart
				v-if="isFormActive === 3"
				:cartList="cart"
				@return="returnBook"
			/>
		</div>
	</div>
</template>
