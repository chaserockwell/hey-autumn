<template>
<div class="test">
	<h1>{{name}}</h1>
</div>
</template>

<script>
export default {
	name: 'test',
	props: ['name'],
	data () {
		return {
			msg: 'This is a test'
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
	font-weight: bold;
	color: red;
}
</style>
