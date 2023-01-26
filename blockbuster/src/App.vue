<script setup>
import MovieList from './components/MovieList.vue'
import Login from './components/Login.vue'
// import { ref } from 'vue'

// const users = ref([
// 	{
// 		name: 'arielVivian',
// 		password: '1234',
// 	},
// 	{
// 		name: 'deivTorres',
// 		password: '987654',
// 	},
// ])

// const movies = ref([
// 	{
// 		movieName: 'Die Hard',
// 		director: 'John McTiernan',
// 		cast: [
// 			{
// 				name: 'Bruce Willis',
// 				movieName: 'John McClane',
// 				imgAct: 'src\assets\bruce.jpg',
// 			},
// 			{
// 				name: 'Alan Rickman',
// 				movieName: 'Hans Gruber',
// 				imgAct: 'src\assets\Alan Rickman.jpg',
// 			},
// 			{
// 				name: 'Bonnie Bedelia',
// 				movieName: 'Holly Gennaro McClane',
// 				imgAct: 'src\assets\bonnie badella.jpg',
// 			},
// 			{
// 				name: 'Reginald VelJohnson',
// 				movieName: 'Sgto al Power',
// 				imgAct: 'src\assets\sgto alpower.jpg',
// 			},
// 		],
// 		imgMovie:
// 			'https://c8.alamy.com/compes/dtgr78/poster-de-pelicula-de-die-hard-pelicula-de-accion-estadounidense-de-1988-dirigida-por-john-mctiernan-protagonizada-por-bruce-willis-dtgr78.jpg',
// 		sinopsis:
// 			'A New York City police officer tries to save his estranged wife and several others taken hostage by terrorists during a Christmas party at the Nakatomi Plaza in Los Angeles.',
// 		rating: 8.2,
// 	},
// 	{
// 		movieName: 'The Bourne Identity',
// 		director: 'Doug Liman',
// 		cast: [
// 			{
// 				name: 'Matt Damon',
// 				movieName: 'Bourne Jason',
// 				imgAct: 'src\assets\mattdamon.jpg',
// 			},
// 			{
// 				name: 'Franka Potente',
// 				movieName: 'Marie',
// 				imgAct: 'src\assets\franka.jpg',
// 			},
// 			{
// 				name: 'Julia Stiles',
// 				movieName: 'Nicky Parsons',
// 				imgAct: 'src\assets\julia.jpg',
// 			},
// 			{
// 				name: 'Chris Cooper',
// 				movieName: 'Alexander Conklin',
// 				imgAct: 'src\assets\chriscooper.jpg',
// 			},
// 			{
// 				name: 'Clive Owen',
// 				movieName: 'Professor',
// 				imgAct: 'src\assets\cliveowen.jpg',
// 			},
// 		],
// 		imgMovie:
// 			'https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcRxS82BNWfAqupS7v8ruj_hQICxMqyWOU9YP4O3cCnbwNAGTvED',
// 		sinopsis:
// 			'A man is picked up by a fishing boat, bullet-riddled and suffering from amnesia, before racing to elude assassins and attempting to regain his memory.',
// 		rating: 7.9,
// 	},
// ])
</script>

<template>
	<div class="flex justify-center">
		<Login />
	</div>
	<MovieList />
</template>
