<!-- En este componente, lo que vamos a hacer es comenzar a reemplazar la forma en la que organizamos data. -->
<template>
	<div>
		<!-- Creamos 2 h2 con la misma idea, mostrar un nombre en pantalla. pero lo hacemos cada uno de una forma diferente. -->
		<h2>Options - {{ o_firstName }}</h2>
		<h2>Composition - {{ c_firstName }}</h2>
		<h2>Composition - {{ greet }}</h2>
	</div>
</template>

<script>
import { ref } from 'vue'
export default {
	//De esta forma es como utilizamos data con composition API, esta forma lo que hace es que sea mucho mas facil de leer a la hora de si tenemos mucha informacion, la forma de programar de composition API, en mucho mas modular.
	name: 'Data',
	setup() {
		const c_firstName = ref('Clark')
		c_firstName.value = 'Diana'
		const greet = `Hello ${c_firstName.value}`
		console.log('c_firstName', c_firstName)
		return {
			c_firstName,
			greet,
		}
	},
	//De esta forma es como armabamos antes data.
	data() {
		return {
			o_firstName: 'Bruce',
		}
	},
}
</script>

<style scoped></style>
