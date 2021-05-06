<template>
	<header>
		<div class="container">
			<img src="../assets/logo.png" alt="" />
		</div>
	</header>
</template>

<script>
export default {
	name: "Header",
};
</script>

<style scoped lang="scss">
@import "../scss/vars";
header {
	background-color: $background-color-one;

	.container {
		height: 80px;
		padding: 10px;
		img {
			height: 100%;
		}
	}
}
</style>
