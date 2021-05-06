<template>
	<div id="app">
		<!-- HEADER -->
		<Header />
		<!-- CONTENT -->
		<Content />
	</div>
</template>

<script>
import Header from "@/components/Header.vue";
import Content from "@/components/Content.vue";

export default {
	name: "App",
	components: { Header, Content },
};
</script>

<style lang="scss">
@import "~@fontsource/montserrat/index.css";
@import "~@fontsource/montserrat/700.css";

@import "@/scss/vars";

* {
	padding: 0;
	margin: 0;
	box-sizing: border-box;
	font-family: "Montserrat", sans-serif;
}

.container {
	max-width: 1500px;
	margin: 0 auto;
}
</style>
