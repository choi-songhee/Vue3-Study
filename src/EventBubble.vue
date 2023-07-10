<template>
	<div>
		<button @click="printEventInfo('hello', $event)">
			inline event handler
		</button>

		<input type="text" @keyup="onkeyupHandler" />

		<div id="modifiers">
			<div @click="clickDiv">
				DIV 영역
				<p @click="clickP">
					P 영역
					<!-- <span @click.stop="clickSpan">span 영역</span> -->
					<span @click="clickSpan">span 영역</span>
					<a href="https://naver.com" @click.prevent.stop="clickA">Link</a>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	setup() {
		const printEventInfo = (message, event) => {
			console.log(message);
			console.log(event.target);
			console.log(event.target.tagName);
		};
		const onkeyupHandler = event => {
			console.log(event.key);
		};

		const clickDiv = () => {
			console.log('clickDiv');
			// location.href = 'https://naver.com';
		};
		const clickP = () => {
			console.log('clickP');
		};
		const clickSpan = () => {
			console.log('clickSpan');
			// alert('좋아요');
		};
		const clickA = () => {
			alert('prevent test');
		};

		return {
			printEventInfo,
			onkeyupHandler,
			clickDiv,
			clickP,
			clickSpan,
			clickA,
		};
	},
};
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
	padding: 30px;
	display: block;
	background-color: #ccc;
}
#modifiers p {
	background-color: #999;
}
#modifiers span {
	background-color: #666;
}
</style>
