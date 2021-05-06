<template>
	<div class="album">
		<div class="album-image">
			<img :src="info.poster" :alt="info.author" />
		</div>

		<div class="album-desc name">{{ info.title }}</div>
		<div class="album-desc author">{{ info.author }}</div>
		<div class="album-desc year">{{ info.year }}</div>
		<div class="album-desc genre">{{ info.genre }}</div>
	</div>
</template>

<script>
export default {
	name: "Album",
	props: ["info"],
};
</script>

<style scoped lang="scss">
@import "../scss/vars";
.album {
	background: $background-color-one;
	width: 100%;
	height: 320px;
	padding: 5px 5px;
	.album-image {
		padding: 10px;
		height: 150px;
		overflow: hidden;
		img {
			max-width: 100%;
		}
	}

	.album-desc {
		padding: 0px 10px;
		max-width: 100%;
		word-wrap: break-word;
		margin-bottom: 10px;
	}
	.album-desc.name {
		text-transform: uppercase;
		color: white;
	}

	.album-desc.author,
	.album-desc.year {
		color: $text-color-two;
		margin-bottom: 5px;
	}
	.album-desc.genre {
		color: white;
		margin-bottom: 5px;
	}
	.album-desc.year,
	.album-desc.genre {
		font-size: 12px;
	}
}

@media screen and (max-width: 989px) {
	.album-image {
		margin-bottom: 20px;
	}
	// .album-desc {
	// 	margin-top: 20px;
	// }
	// .album-desc.author,
	// .album-desc.year,
	// .album-desc.genre {
	// 	margin-top: 0;
	// }
}
</style>
