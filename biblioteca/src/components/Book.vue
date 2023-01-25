<script setup>
import { defineProps } from 'vue'
import Card from './Card.vue'
import Button from './Button.vue'

defineProps({
	book: {
		type: Object,
		required: true,
	},
	isBuy: {
		type: Boolean,
		default: false,
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
		<div class="flex justify-center">
			<img :src="book.url" />
		</div>
		<Button
			@click="$emit('submit', book)"
			class="focus:outline-none text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-10 ml-10 mt-5 mb-2"
		>
			{{ isBuy ? 'Return Product' : 'Buy Book' }}
		</Button>
	</Card>
</template>
