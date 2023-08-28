<template><div></div></template>

<script>
export default {
	props: ['startX', 'startY', 'endX', 'endY', 'lineWidth'],
	methods: {
		draw(ctx) {
			ctx.beginPath();

			ctx.moveTo(this.startX, this.startY);
			ctx.lineTo(this.endX, this.endY);

			if (this.lineWidth < 3) {
				ctx.lineWidth = 0.5;
			} else if (this.lineWidth < 7) {
				ctx.lineWidth = this.lineWidth * 0.7;
			} else if (this.lineWidth < 10) {
				ctx.lineWidth = this.lineWidth * 0.9;
			} else {
				ctx.lineWidth = this.lineWidth;
			}

			ctx.fillStyle = '#000000';
			ctx.strokeStyle = '#000000';

			ctx.stroke();
			ctx.closePath();
		},
	},
};
</script>
<style lang="scss" scoped></style>
