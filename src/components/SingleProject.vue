<template>
	<div class="title">
		<h1 class="title">{{ project.title }}</h1>
		<div class="title" v-if="showDeadline">
			<p>{{ project.deadline }}</p>
		</div>
		<p>{{ data }}</p>
		<button @click="showDeadline = !showDeadline">view</button>
		<div class="buttons">
			<button>done</button>
			<button @click="deleteD">delete</button>
			<button>edit</button>
		</div>
	</div>
</template>

<script setup>
// import
import axios from 'axios';
import { ref } from 'vue';

// variable
const props = defineProps(['project']);
let showDeadline = ref(false);
let data = new Date();

// functions

const deleteD = async () => {
	return await axios.delete(
		`http://localhost:3000/projects/${props.project.id}`
	);
};
</script>

<style scoped>
.title {
	padding: 10px;
	border: 1px solid;
	border-radius: 3px;
}

.buttons {
	display: flex;
	margin-top: 5px;
	gap: 4px;
}
.green {
	background-color: brown;
}

span {
	border: 1px solid;
}
</style>
