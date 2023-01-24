<script setup>
import Button from './Button.vue'
//llamamos al defineemits, para enviar un evento desde una funcion.
import { defineEmits, ref } from 'vue'
//creamos la variable donde almacenamos el nuevo libro
const newBook = ref({})
//creamos la variable que nos permite usar la funcion con el evento.
const emit = defineEmits(['submit'])
// funcion que reemplaza al evento que teniamos en el boton
function handleSubmit() {
	console.log(!newBook.value.bookName)
	if (
		!newBook.value.bookName ||
		!newBook.value.author ||
		!newBook.value.price ||
		!newBook.value.url
	) {
		alert('This form is not valid')
		return
	}

	emit('submit', newBook.value)
	newBook.value = {}
}
</script>

<template>
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
				@keyup.enter="handleSubmit"
			/>
		</div>
		<div>
			<input
				type="text"
				placeholder="Autor"
				v-model="newBook.author"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
				@keyup.enter="handleSubmit"
			/>
		</div>
		<div>
			<input
				type="text"
				placeholder="Price"
				v-model="newBook.price"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
				@keyup.enter="handleSubmit"
			/>
		</div>
		<div>
			<input
				type="text"
				placeholder="Img. URL"
				v-model="newBook.url"
				class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
				@keyup.enter="handleSubmit"
			/>
		</div>
		<div class="flex justify-center">
			<Button
				class="inline focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mb-2"
				@click="handleSubmit"
			>
				Submit</Button
			>
		</div>
	</div>
</template>
