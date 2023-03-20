<template>
	<div class="result-block">
		<h3>Your Result</h3>
		<section class="circle-result">
			<span class="final-result pa">{{ totalScore }}</span>
			<span class="total-result pa">of 100</span>
		</section>

		<section class="message-result">
			<h2>Great</h2>
			<p>
				You scored higher than 65% of the people who have taken these tests.
			</p>
		</section>
	</div>
</template>
<script setup>
	const props = defineProps({
		totalScore: {
			type: Number,
			default: 0,
		},
	});
</script>

<style scoped>
	.result-block {
		z-index: 1;
		background: rgb(46, 43, 233);
		background: linear-gradient(
			0deg,
			rgba(46, 43, 233, 1) 10%,
			rgba(120, 87, 255, 1) 100%
		);
		padding: 40px;
		border-radius: 30px;
	}
	h3 {
		text-align: center;
		color: var(--lightLavender);
		font-size: 21px;
	}

	.circle-result {
		position: relative;
		background: rgb(46, 43, 233);
		background: linear-gradient(
			0deg,
			rgba(46, 43, 233, 1) 3%,
			rgba(78, 33, 202, 1) 50%
		);

		border-radius: 50%;
		height: 200px;
		width: 200px;
		margin: 40px auto;
	}

	.final-result {
		font-size: 72px;
		color: var(--paleBlue);
		top: 40px;
		left: 60px;
		font-weight: 600;
	}

	.total-result {
		color: var(--lightLavender);
		bottom: 50px;
		left: 75px;
		font-weight: 600;
	}

	.message-result {
		color: var(--paleBlue);
		text-align: center;
	}

	p {
		margin-top: 15px;
		font-size: 19px;
		color: var(--lightLavender);
	}
</style>
