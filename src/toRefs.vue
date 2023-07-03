<template>
	<div>
		<p>author: {{ author }}</p>
		<p>title: {{ title }}</p>
	</div>
</template>

<script>
import { reactive, toRefs, toRef } from 'vue';
export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 이 책을 지금 바로 읽습니다',
			price: '무료',
		});

		// 구조분해할당
		const { author, title } = toRefs(book); // 구조분해할당을 할때 반응형 유지
		const year = toRef(book, 'year'); // 하나만 가져오고 싶은 경우 toRef 사용
		console.log(typeof title.value);
		return {
			author,
			title,
			book,
			year,
		};
	},
};
</script>

<style lang="scss" scoped></style>
