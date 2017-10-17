<template>
  <div id="app" class="app-base">
		<div class="app-nav">
			<app-nav></app-nav>
		</div>
		<div class="app-body">
    	<router-view></router-view>
		</div>
		<div class="app-footer">
			<app-footer></app-footer>
		</div>
  </div>
</template>

<script>
import AppFooter from './components/Footer.vue';
import AppNav from './components/Nav.vue';

export default {
	name: 'app',
	components: {
		AppFooter,
		AppNav
	}
}
</script>

<style>
body {
	margin: 0;
}

.app-base {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
	display: grid;
	grid-template-rows: auto 45px;
	min-height: 100vh;
}

.app-nav,
.app-footer {
	width: 100%;
}

.app-nav {
	position: fixed;
	top: 0;
	left: 0;
	height: 60px;
	z-index: 1000;
	background-color: rgba(0, 0, 0, .75);
}

.app-footer {
	height: 100%;
	position: relative;

}

</style>
