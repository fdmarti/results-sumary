<template>
	<div class="card" v-if="isLoading">Loading...</div>

	<div class="card" v-else>
		<Result class="block" :totalScore="totalScore"/>
		<Summary class="block" :scores="scores" />
	</div>
</template>
<script setup>
	import { ref } from 'vue';
	import Result from './Result.vue';
	import Summary from './Summary.vue';

	const totalScore = ref(0);
	const scores = ref([]);
	const isLoading = ref(true);

	const getDataFromJson = async () => {
		const result = await fetch('../../data.json');
		const data = await result.json();
		scores.value = data;

		calcProm();
		isLoading.value = false;
	};

	const calcProm = () => {
		let total = 0;
		scores.value.forEach((el) => {
			total = total + el.score;
		});
		totalScore.value = Math.floor(total / scores.value.length);
	};

	getDataFromJson();
</script>

<style scoped>
	.card {
		display: flex;
		justify-content: center;
		padding: 60px 0;
	}

	.block {
		flex-grow: 1;
		width: 420px;
	}

	@media (max-width: 992px) {
		.card {
			flex-direction: column;
		}

		.block {
			width: auto;
		}
	}
</style>
