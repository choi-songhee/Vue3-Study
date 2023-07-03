<template>
	<div>
		<p :class="{ active: isActive, 'has-error': hasError }">Text</p>
		<p :class="[activeClass, errorClass]">배열로 바인딩</p>
		<button @click="toggleClass">Toggle</button>
		<button @click="hasError = !hasError">Toggle Error</button>
	</div>
</template>

<script>
import { ref, computed } from 'vue';
export default {
	setup() {
		const isActive = ref(false);
		const toggleClass = () => {
			isActive.value = !isActive.value;
		};
		const hasError = ref(false);

		// 바인딩되는 클래스가 많은 경우 object로 빼서 사용할 수 있음
		// const classObject = reactive({
		// 	active: true,
		// 	'has-error': false,
		// });

		// computed로 사용한 코드 : 조건이 여러개 필요한 경우
		const classObject = computed(() => {
			return {
				active: true && true,
				'has-error': false,
				'text-blue': true,
			};
		});

		const activeClass = ref('active');
		const errorClass = ref('error');

		return {
			isActive,
			toggleClass,
			hasError,
			classObject,
			activeClass,
			errorClass,
		};
	},
};
</script>

<style scoped>
.active {
	font-weight: 700;
	color: aquamarine;
}
.has-error {
	font-weight: 800;
	color: crimson;
}
</style>
