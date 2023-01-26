<script setup>
//imports

import Button from './Button.vue'
import { ref } from 'vue'

//Creamos la variable, utilizamos ref para que se actualice.

const showPassword = ref(false)

//Creamos la funcion para cambiar el valor booleano, donde positivo es mostrar password y negativo ocultarlo, por eso mismo inciamos la variable en falsa.

function showPass() {
	console.log(showPassword)
	showPassword.value = !showPassword.value
	console.log(showPassword)
}
</script>
<template>
	<div class="pt-8">
		<div
			class="card max-w-sm bg-white border border-gray-200 rounded-lg shadow-md shadow p-3 text-center md:text-base text-sm bg-cyan-300"
		>
			<label><h2 class="font-semibold">UserName</h2> </label>
			<input class="border-solid border-2 rounded-md px-3 text-center" />
			<label><h2 class="font-semibold">Password</h2> </label>
			<!-- Creamos el vinculo donde podemos utilizar el if, siempre que sea 2 variables, podemos utilizar este metodo dentro del objeto que queremos modificarle algun estilo, en este caso mostrar o no un input -->
			<input
				:type="showPassword ? 'text' : 'password'"
				class="border-solid border-2 rounded-md text-center"
			/>
			<!-- LLamamos la funcion creada y la conectamos al boton a traves del @click -->
			<Button
				class="border-solid border-2 rounded-md font-semibold px-2 bg-sky-500 shadow-md shadow hover:bg-teal-300"
				@click="showPass"
				>*</Button
			>

			<div class="pt-4">
				<Button
					class="border-solid border-2 rounded-md font-semibold px-2 py-2 bg-sky-500 shadow-md shadow hover:bg-teal-300"
				>
					Login
				</Button>
			</div>
		</div>
	</div>
</template>
