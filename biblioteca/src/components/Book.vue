<script setup>
import { defineProps } from 'vue'

defineProps({
	book: {
		type: Object,
		required: true,
	},
})
</script>

<template>
	<div>
		<h5>{{ book }}</h5>
	</div>
</template>
