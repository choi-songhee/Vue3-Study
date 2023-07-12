<template>
	<div>
		<form @submit.prevent>
			<input v-model.lazy="title" type="text" placeholder="title" />
			<textarea v-model.lazy="contents" placeholder="contents"></textarea>
			<button @click="save(title, contents)">Save</button>
		</form>
	</div>
</template>

<script>
import { ref, watchEffect } from 'vue';
export default {
	setup() {
		const title = ref('');
		const contents = ref('');
		const save = (title, contents) => {
			console.log(`저장: ${title}, ${contents}`);
		};

		// watch 보다 덜 명시적
		watchEffect(() => {
			save(title.value, contents.value);
			console.log(title.value);
			console.log(contents.value);
		});

		return {
			title,
			contents,
			save,
		};
	},
};
</script>

<style lang="scss" scoped></style>
