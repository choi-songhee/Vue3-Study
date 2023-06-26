<template>
	<div></div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
	setup() {
		// ref -> Object 에서 사용
		const count = ref(0);
		const state = reactive({
			count,
		});
		count.value++;
		// console.log(count.value);
		// console.log(state.count);

		// ref -> Array 에서 사용
		const message = ref('hello');
		const arr = reactive([message]);
		console.log(arr[0].value); // 배열에서 다시 접근하려면 .value 붙음

		return {
			count,
			state,
			message,
			arr,
		};
	},
};
</script>

<style lang="scss" scoped></style>
