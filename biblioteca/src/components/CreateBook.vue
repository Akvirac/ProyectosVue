<script setup>
import ButtonLive from './ButtonLive.vue'
const newBook = {}
</script>

<template>
	<div>
		<!-- {{ book }} -->
		<div
			class="max-w-sm bg-white border border-gray-200 rounded-lg shadow-md place-items-center"
		>
			<h2 class="text-center">New Book</h2>

			<label></label>
			<div>
				<input
					type="text"
					placeholder="Book Name"
					class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5"
					v-model="newBook.bookName"
				/>
			</div>
			<div>
				<input
					type="text"
					placeholder="Autor"
					v-model="newBook.author"
					class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5"
				/>
			</div>
			<div>
				<input
					type="text"
					placeholder="Book price"
					v-model="newBook.price"
					class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5"
				/>
			</div>
			<div>
				<input
					type="text"
					placeholder="Img URL"
					v-model="newBook.url"
					class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5"
				/>
			</div>
			<div>
				<ButtonLive
					class="justify-center focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
					@click="$emit('submit', newBook)"
					>Submit</ButtonLive
				>
			</div>
		</div>
	</div>
</template>
