<template>
	<div class="footer">
		<p>&copy; Hey Autumn | 2017</p>
		<div class="logo"></div>
	</div>
</template>

<script>
export default {
	name: 'app-footer'
}
</script>

<style lang="scss" scoped>
	.footer {
		background-color: black;
		color: white;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 30px;
	}

	.logo {
		height: 25px;
		width: 25px;
		border: 2px solid white;
		border-radius: 50%;
	}
</style>

