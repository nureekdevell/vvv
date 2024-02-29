<template>
	<RouterLink to="/">Home</RouterLink>
	<RouterLink to="/about">About</RouterLink>
	<RouterView />
</template>

<script setup>
import { RouterView } from 'vue-router';
</script>

<style lang="scss" scoped></style>
