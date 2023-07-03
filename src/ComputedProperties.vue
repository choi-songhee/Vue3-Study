<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있나요?</h3>
		<p>{{ hasLecture }}</p>
		<p>{{ hasLecture }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>
		<button @click="counter++">Counter: {{ counter }}</button>
		<h2>{{ fullName }}</h2>
	</div>
</template>

<script>
import { ref, reactive, computed } from 'vue';
export default {
	setup() {
		const teacher = reactive({
			name: 'song',
			lectures: ['html/css', 'javascript'],
		});

		const hasLecture = computed(() => {
			//computed는 한번 계산된 결과를 캐시하기 때문에 성능면에서 유리
			// console.log('computed');
			return teacher.lectures.length > 0 ? 'Yes' : 'No';
		});
		const existLecture = () => {
			// console.log('method');
			return teacher.lectures.length > 0 ? 'Yes' : 'No';
		};

		const counter = ref(0);

		const FirstName = ref('choi');
		const LastName = ref('song');

		// 수정이 필요한경우 getter, setter 사용
		const fullName = computed({
			get() {
				return FirstName.value + ' ' + LastName.value;
			},
			set(value) {
				[FirstName.value, LastName.value] = value.split(' ');
			},
		});
		fullName.value = '짐 코딩';

		return {
			teacher,
			hasLecture,
			existLecture,
			counter,
			FirstName,
			LastName,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>
