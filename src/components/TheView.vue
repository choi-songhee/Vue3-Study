<template>
	<main>
		<div class="container text-center py-4">
			<div class="row g-3">
				<div v-for="(post, idx) in posts" :key="idx" class="col col-4">
					<CardItem
						:title="post.title"
						:contents="post.contents"
						:type="post.type"
					/>
				</div>
			</div>
		</div>
	</main>
</template>

<script>
import CardItem from './CardItem.vue';
import { reactive } from 'vue';
export default {
	components: {
		CardItem,
	},
	setup() {
		const post = reactive({
			title: 'title2',
			contents: 'contents2',
		});
		const posts = reactive([
			{
				type: 'news',
				title: 'title1',
				contents: 'contents1',
			},
			{
				type: '',
				title: 'title2',
				contents: 'contents2',
			},
			{
				title: 'title3',
				contents: 'contents3',
			},
			{
				title: 'title4',
				contents: 'contents4',
			},
			{
				title: 'title5',
				contents: 'contents5',
			},
		]);

		const followUser = id => {
			const newFollowingList = this.state.users.map(user => {
				if (user.userId === id) {
					user.isFollo;
				}
			});
		};
		return {
			post,
			posts,
			followUser,
		};
	},
};
</script>
<!-- 공존가능 -->
<!-- <script setup>
</script> -->

<style lang="scss" scoped></style>
