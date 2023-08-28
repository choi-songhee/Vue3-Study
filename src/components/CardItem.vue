<template>
	<div class="card">
		<div class="card-body">
			<!-- type : news, notice -->
			<span class="badge bg-secondary">
				{{ type === 'news' ? '뉴스' : '공지사항' }}
			</span>
			<h5 class="card-title mt-2">{{ title }}</h5>
			<p class="card-text">
				{{ contents }}
			</p>
			<a href="#" class="btn btn-primary">Go somewhere</a>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		type: {
			type: String,
			default: 'news',
		},
		title: {
			type: String,
			required: true,
		},
		contents: {
			type: String,
			required: true,
		},
		isLike: {
			type: Boolean,
			defuault: false,
		},
	},
	setup() {
		return {};
	},
};
</script>

<!-- module 속성을 지정하게 되면 css모듈로 컴파일 되고 css 클래스를 $style 객체의 속성으로 노출 -->
<style></style>
