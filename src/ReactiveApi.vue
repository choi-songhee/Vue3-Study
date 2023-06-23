<template>
	<div>
		<h2>Reactive Message</h2>
		<p>{{ reactiveMessage }}</p>
		<button @click="addReactiveMessage">Add Message</button>
		<h2>Normal Message</h2>
		<p>{{ normalMessage }}</p>
		<button @click="addNormalMessage">Add Message</button>
	</div>
</template>

<script>
import { ref, isRef, onMounted, onBeforeMount } from 'vue';
export default {
	setup() {
		console.log('setup()');

		const reactiveMessage = ref('Reactive Message');
		const addReactiveMessage = () => {
			reactiveMessage.value = reactiveMessage.value + '!';
		};
		console.log(isRef(reactiveMessage)); // isRef: 반응형 데이터인지 확인

		const normalMessage = 'normal message';
		const addNormalMessage = () => {
			normalMessage.value = normalMessage.value + '!';
		};
		console.log(isRef(normalMessage));

		onMounted(() => {
			console.log('onMounted');
		});
		onBeforeMount(() => {
			console.log('onBeforeMount');
		});

		return {
			reactiveMessage,
			normalMessage,
			addReactiveMessage,
			addNormalMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
