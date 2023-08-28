<template>
	<TheNav />
	<TheView />
	<TreeInteraction />
</template>

<script>
import TheNav from './components/TheNav.vue';
import TheView from './components/TheView.vue';
import TreeInteraction from './components/TreeInteraction.vue';
export default {
	components: {
		TheNav,
		TheView,
		TreeInteraction,
	},
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
