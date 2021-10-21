<template>
	<h1>{{ msg }}</h1>
	<h2>Filter LearnVue Articles</h2>
	<input type="text" placeholder="Filter Search" v-model="query" />
	<br />
	<br />
	<button @click="reset">Reset</button>
	<br />
	<br />
	<search-results :query="query" />
	<span style="margin-bottom: 40px; display: block" />
</template>

<script>
	import { ref } from "vue"
	import SearchResults from "./SearchResults.vue"
	export default {
		name: "HelloWorld",
		components: { SearchResults },
		props: {
			msg: String
		},
		setup() {
			const query = ref("")
			const reset = (evt) => {
				query.value = "" //clear the query
			}
			return { reset, query }
		}
	}
</script>
