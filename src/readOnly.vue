<template>
	<div></div>
</template>

<script>
import { reactive, readonly } from 'vue';
export default {
	setup() {
		const original = reactive({
			count: 0,
		});
		// 반응형 api
		const copy = readonly(original); // copy를 원하는 반응형 객체를 넣어줌
		original.count++;
		console.log(original.count);
		copy.count++;
		console.log(copy.count); // readonly 는 값 변경 불가
		return {
			original,
			copy,
		};
	},
};
</script>

<style lang="scss" scoped></style>
