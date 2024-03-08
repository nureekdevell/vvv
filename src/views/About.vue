<template>
	<div>
		<form @submit.prevent="fromSubmit">
			<label for=""
				><input
					id="Moscow"
					v-model="rest"
					type="checkbox"
					value="Moscow"
				/>Moscow</label
			>
			<label for=""
				><input
					id=""
					v-model="rest"
					type="checkbox"
					value="Tashkent"
				/>Tashkent</label
			>
			<label for=""
				><input
					id="Moscow"
					v-model="rest"
					type="checkbox"
					value="Qarshi"
				/>Qarshi</label
			>
			<label for=""
				><input
					id="Moscow"
					v-model="rest"
					type="checkbox"
					value="Qarshi"
				/>Qarshi</label
			>
			<button type="submit">Submit</button>
		</form>
	</div>
</template>

<script setup>
import { ref } from 'vue';

const rest = ref([]);

const fromSubmit = () => {
	console.log('submit', rest);
};
</script>

<style lang="scss" scoped></style>
