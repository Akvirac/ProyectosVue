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
		<Book v-for="item in books" :key="item" :book="item" />
	</ul>
</template>
