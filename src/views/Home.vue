<template>
	<div>
		<ul>
			<li v-for="project of projects" :key="project.id">
				<h2>{{ project.id }}</h2>
				<h2>{{ project.title }}</h2>
				<h2>{{ project.deadline }}</h2>
			</li>
		</ul>
	</div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import axios from 'axios';

let projects = ref([]);

onMounted(async () => {
	let response = await axios.get('http://localhost:3000/projects');
	projects.value = response.data;
	// let respone = await fetch('http://localhost:3000/projects');
	// let data = await respone.json();
	// for (let element of data) {
	// 	console.log(element);
	// }
});
</script>

<style lang="scss" scoped></style>
