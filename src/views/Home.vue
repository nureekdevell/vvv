<template>
	<div class="home">
		<div v-for="project of projects" :key="project.id">
			<SingleProject :project="project" />
		</div>
	</div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import axios from 'axios';
import SingleProject from '@/components/SingleProject.vue';

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
const deleteD = async () => {
	return await axios.delete(`http://localhost:3000/projects/${project.id}`);
};

const editP = () => {
	console.log('Salom');
};
</script>

<style lang="scss" scoped></style>
