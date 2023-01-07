<script setup>
import { defineProps } from 'vue'

defineProps({
	book: {
		type: Array,
		required: true,
	},
})
</script>

<template>
	<div>
		<li>{{ book }}</li>
	</div>
</template>
