<template>
	<canvas ref="canvas" />
</template>

<script>
import Tree from './TreeItem.vue';
export default {
	mounted() {
		this.canvas = this.$refs.canvas;
		this.ctx = this.canvas.getContext('2d');
		this.pixelRatio = window.devicePixelRatio > 1 ? 2 : 1;

		window.addEventListener('resize', this.resize, false);
		this.resize();

		new Tree(this.ctx, this.stageWidth / 2, this.stageHeight);
	},
	methods: {
		resize() {
			this.stageWidth = document.body.clientWidth;
			this.stageHeight = document.body.clientHeight;

			this.canvas.width = this.stageWidth * this.pixelRatio;
			this.canvas.height = this.stageHeight * this.pixelRatio;
			this.ctx.scale(this.pixelRatio, this.pixelRatio);

			this.ctx.clearRect(0, 0, this.stageWidth, this.stageHeight);
		},
	},
};
</script>

<style lang="scss" scoped></style>
