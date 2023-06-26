<template>
	<div>
		<p>{{ message }}</p>
		<button @click="addMsg">Add Click</button>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		// reactive 함수는 객체나 배열과 같이 reference 타입의 반응형 객체를 선언하는 함수 이기 때문에 primitive type을 다룰수 없음
		// reactive 함수를 사용하려면 객체로 바꿔서 사용
		// ref 메소드 = number, string, boolean 을 반응형으로 만들때 사용
		let message = ref('text reactive');

		const addMsg = () => {
			message.value = message.value + '!';
		};

		console.log(message);
		console.log(typeof message.value);
		return {
			message,
			addMsg,
		};
	},
};
</script>

<style lang="scss" scoped></style>
