<template>
	<div>
		{{ counter }}
		<button @click="increment">click</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	// 매개변수로 props, context 전달
	setup() {
		const counter = ref(0);
		const increment = () => {
			counter.value++;
		};
		return {
			counter, // return 하지 않으면 사용못함
			increment,
		};
	},
};
</script>

<style lang="scss" scoped></style>
