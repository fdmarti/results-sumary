<template>
	<section class="bullet" :class="bg">
		<div class="title-bullet">
			<img
				:src="`${imagePath}`"
				:alt="`Icon of the ${text} bullet`"
				class="icon-bullet"
			/>
			<span class="text-bullet">{{ text }}</span>
		</div>
		<div class="result-bullet">
			{{ score }} <span class="blurryText"> / 100</span>
		</div>
	</section>
</template>
<script setup>
	import { computed } from 'vue';

	const props = defineProps({
		icon: {
			type: String,
			default: 'icon-reaction.svg',
		},
		text: {
			type: String,
			default: 'Icon Name',
		},
		score: {
			type: String,
			default: '100',
		},
		bg: String,
	});

	const imagePath = computed(() => `${props.icon}`);
</script>
<style scoped>
	.bullet {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 20px;
		margin: 20px 30px;
		border-radius: 25px;
		position: relative;
	}

	.icon-bullet {
		position: relative;
		top: 5px;
	}

	.text-bullet {
		margin-left: 10px;
		font-weight: 600;
	}

	.result-bullet {
		color: var(--darkGreyBlue);
		font-weight: 800;
	}
</style>
