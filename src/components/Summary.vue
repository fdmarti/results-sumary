<template>
	<div class="summary-block">
		<h3>Summary</h3>
		<div>
			<Bullet
				v-for="(bullet, index) in scores"
				:key="index"
				:icon="bullet.icon"
				:text="bullet.category"
				:score="bullet.score"
				:bg="bullet.bg"
			/>
			<Button text="Continue" />
		</div>
	</div>
</template>
<script setup>
	import Bullet from './BulletComponent.vue';
	import Button from './ButtonComponent.vue';

	const props = defineProps({
		scores: Object,
	});
</script>
<style scoped>
	.summary-block {
		box-shadow: 0 0 15px 5px var(--lightLavender);
		position: relative;
		background: var(--white);
		padding: 40px;
		border-radius: 30px;
		left: -45px;
	}

	h3 {
		margin-left: 30px;
		color: #303b5a;
		font-size: 21px;
	}

	@media (max-width: 992px) {
		.summary-block {
			left: 0;
		}
	}
</style>
