<script setup>
import { defineProps } from 'vue'
import Book from './Book.vue'
defineProps({
	books: {
		type: Array,
		required: true,
	},
})
</script>

<template>
	<ul>
		<Book v-for="book in books" :key="book" :book="book" />
		hola
	</ul>
</template>
