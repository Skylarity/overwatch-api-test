<template>
	<h1>Overwatch API Test</h1>
	<pre>
		{{ formattedData }}
	</pre>
</template>

<script>
export default {
	name: 'hello',
	data () {
		return {
			data: {}
		}
	},
	mounted: function() {
		this.getBlob()
	},
	methods: {
		getBlob: function() {
			this.$http.get('https://owapi.net/api/v3/u/Skylarity-1114/blob')
				.then(function(result) {
					this.data = result.body
				})
		}
	},
	computed: {
		formattedData: function() {
			return JSON.stringify(data)
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
