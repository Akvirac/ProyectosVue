<template>
	<Data />
</template>

<script>
//importamos nuestros componentes.
import Data from './components/Data.vue'
export default {
	name: 'App',
	components: {
		//Agregamos el componente a la lista.
		Data,
	},
	data() {
		return {}
	},
	methods: {},
}
</script>

<style scoped>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
.underline {
	text-decoration: underline;
}
.promoted {
	font-style: italic;
}
.new {
	color: green;
}
.sold-out {
	color: red;
}
</style>
