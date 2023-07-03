<template>
	<div v-memo="[subscribe, likes]">
		<!-- v-memo : 성능과 관련된 디렉티브 - 성능최적화가 필요한 경우에 사용 -->
		<!-- v-for에서 목록을 렌더링 할때 리스트가 1000개 이상인 경우에 사용하면 좋음 -->
		<!-- 배열안에 반응형 데이터 변경이 일어났을때만 업데이트 -->
		<p>subscribe: {{ subscribe }}</p>
		<p>views: {{ views }}</p>
		<p>likes: {{ likes }}</p>
	</div>
	<button @click="subscribe++">Sub++</button>
	<button @click="views++">Views++</button>
	<button @click="likes++">Likes++</button>

	<!-- 비교 코드 -->
	<div>
		<p>subscribe: {{ subscribe }}</p>
		<p>views: {{ views }}</p>
		<p>likes: {{ likes }}</p>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const subscribe = ref(4000);
		const views = ref(400);
		const likes = ref(2);

		return {
			subscribe,
			views,
			likes,
		};
	},
};
</script>

<style lang="scss" scoped></style>
