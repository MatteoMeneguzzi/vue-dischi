<template>
	<main>
		<div class="container" v-if="!loading">
			<div
				class="box"
				v-for="(album, index) in albumList.response"
				:key="index"
			>
				<Album :info="album" />
			</div>
		</div>
		<div v-else class="loader">Loading...</div>
	</main>
</template>

<script>
import axios from "axios";
import Album from "../components/Album";

export default {
	name: "Content",
	components: { Album },
	data() {
		return {
			apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
			albumList: [],
			loading: true,
		};
	},
	created() {
		this.getAlbums();
	},
	methods: {
		getAlbums() {
			// API Call
			axios
				.get(this.apiURL)
				.then((result) => {
					console.log(result.data);
					this.albumList = result.data;
					this.loading = false;
				})
				.catch((err) => {
					console.log("ERRORE: ", err);
				});
		},
	},
};
</script>

<style scoped lang="scss">
@import "../scss/vars";
main {
	background-color: $background-color-two;

	.container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		padding: 50px;
		.box {
			width: calc(100% / 8 - 20px);
			margin-right: 10px;
			margin-left: 10px;
			margin-top: 20px;
			text-align: center;
		}
	}
}

@media screen and (max-width: 1199px) {
	main {
		background-color: $background-color-two;

		.container {
			display: flex;
			justify-content: center;
			flex-wrap: wrap;
			padding: 50px;
			.box {
				width: calc(100% / 6 - 20px);
				margin-right: 10px;
				margin-left: 10px;
				margin-top: 20px;
				text-align: center;
			}
		}
	}
}

@media screen and (max-width: 989px) {
	main {
		background-color: $background-color-two;

		.container {
			display: flex;
			justify-content: center;
			flex-wrap: wrap;
			padding: 50px;
			.box {
				width: calc(100% / 4 - 20px);
				margin-right: 10px;
				margin-left: 10px;
				margin-top: 20px;
				text-align: center;
			}
		}
	}
}
</style>
