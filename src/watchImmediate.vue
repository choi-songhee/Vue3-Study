<template>
	<div>
		<p>{{ message }}</p>
		<p>{{ reverseMessage }}</p>
	</div>
</template>

<script>
import { ref, watch } from 'vue';
export default {
	setup() {
		const message = ref('hello');
		const reverseMessage = ref('');

		const reverseFunction = () => {
			reverseMessage.value = message.value.split('').reverse().join('');
		};

		// watch(message, reverseFunction, {
		// 	immediate: true, // 최초 한번 즉시실행
		// });
		watch(message, reverseFunction);
		reverseFunction();

		return {
			message,
			reverseMessage,
			reverseFunction,
		};
	},
};
</script>

<style lang="scss" scoped></style>
