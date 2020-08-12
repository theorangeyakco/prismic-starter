<template>
	<div>
		<h1>Hi</h1>
		<div v-for="index in fields.pictures">
			<img :src="index.data.image.url" alt="" />
			<h1>{{ index.data.title[0].text }}</h1>
			<p>{{ index.data.description[0].text }}</p>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			fields: {
				pictures: [],
			},
		};
	},
	methods: {
		// This is an example query, the important part is above.
		getContent() {
			this.$prismic.client
				.query(this.$prismic.Predicates.at("document.type", "picture"))
				.then((document) => {
					this.fields.pictures = document.results;
					console.log(document.results);
				});
		},
	},
	created() {
		this.getContent();
	},
};
</script>

<style scoped>
img {
	width: 100vw;
}
</style>
