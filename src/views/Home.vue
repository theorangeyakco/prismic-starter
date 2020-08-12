<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png" />
		<HelloWorld msg="Welcome to Your Vue.js App" />
		<PrismicContent></PrismicContent>
	</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import PrismicContent from "@/components/PrismicContent.vue";

export default {
	name: "Home",
	components: {
		HelloWorld,
		PrismicContent,
	},
};
</script>
