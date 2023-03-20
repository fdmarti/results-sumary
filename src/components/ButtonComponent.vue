<template>
	<section class="button-section">
		<button class="btn">{{ text }}</button>
	</section>
</template>
<script setup>
	const props = defineProps({
		text: {
			type: String,
			default: 'Button Text',
		},
	});
</script>
<style scoped>
	.button-section {
		display: flex;
		justify-content: center;
	}

	.btn {
		text-align: center;
		background-color: var(--darkGreyBlue);
		color: var(--white);
		border: none;
		border-radius: 25px;
		padding: 15px 25px;
		font-size: 17px;
		font-family: var(--mainFont);
        width: 85%;
	}

	.btn:hover {
		cursor: pointer;
		background-color: #243155;
	}
</style>
