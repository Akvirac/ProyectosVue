<script setup>
import { defineProps } from 'vue'
import Card from './Card.vue'
import ButtonLive from './ButtonLive.vue'

defineProps({
	book: {
		type: Object,
		required: true,
	},
})
</script>

<template>
	<Card>
		<h2>
			<span class="font-bold"> Book Name: </span>
			{{ book.bookName }}
		</h2>

		<h2>
			<span class="font-bold"> Author: </span>

			{{ book.author }}
		</h2>
		<h2>
			<span class="font-bold"> Price: </span>
			{{ book.price }}
		</h2>
		<h2 class="font-bold">Book Cover</h2>
		<img :src="book.url" />
		<ButtonLive
			@click="$emit('buy', book)"
			class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-10 ml-10 mt-5 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
		>
			Buy Book
		</ButtonLive>
	</Card>
</template>
