<template>
	<div>
		<button @click="increment">Click {{ state.count }}</button>
		<button @click="increment">Click {{ state.deep.count }}</button>
	</div>
</template>

<script>
import { reactive } from 'vue';
export default {
	setup() {
		// 반응형 객체로 만들어줌
		const state = reactive({
			count: 0,
			deep: {
				count: 0,
			},
		});
		const increment = () => {
			state.count++;
			state.deep.count++;
		};

		return {
			state,
			increment,
		};
	},
};
</script>

<style lang="scss" scoped></style>
