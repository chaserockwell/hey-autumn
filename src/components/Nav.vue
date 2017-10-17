<template>
<div>
	<div class="hamburger-container" @click="toggleSideMenu">
		<div class="hamburger" :class="{opened: isMenuOpen}">
			<span></span>
			<span></span>
			<span></span>
			<p class="menu">menu</p>
			<p class="close">close</p>
		</div>
	</div>
	<div class="side-menu" :class="{closed: !isMenuOpen, opened: isMenuOpen}">
		<div class="close">

		</div>
		<div class="logo">
			<div class="logo-container">
				<p>logo</p>
			</div>
		</div>
		<div class="links">
			<ul>
				<li><router-link @click.native="toggleSideMenu" to="/" class="menu-link">HOME</router-link></li>
				<li><router-link @click.native="toggleSideMenu" to="/blog/food" class="menu-link">FOOD</router-link></li>
				<li><router-link @click.native="toggleSideMenu" to="/blog/lifestyle" class="menu-link">LIFESTYLE</router-link></li>
				<li><router-link @click.native="toggleSideMenu" to="/blog/travel" class="menu-link">TRAVEL</router-link></li>
				<li><router-link @click.native="toggleSideMenu" to="/about" class="menu-link">ABOUT US</router-link></li>
			</ul>
		</div>
		<div class="footer">
			<p class="follow-us">Follow Us</p>
			<div class="icons">
				<div class="icon"><img src="http://www.freepngimg.com/download/facebook/8-2-facebook-transparent.png" alt=""></div>
				<div class="icon"><img src="http://huboncampus.com/wp-content/themes/hub-tucson2/images/social/twitter/twitter-2048-black.png" alt=""></div>
				<div class="icon"><img src="https://s3.amazonaws.com/freebiesupply/large/2x/instagram-logo-black-transparent.png" alt=""></div>
			</div>
		</div>
	</div>
</div>
</template>

<script>
var vm = {
	name: 'app-nav',
	data() {
		return {

			isMenuOpen: false
		}
	},
	methods: {
		toggleSideMenu() {
			this.isMenuOpen = !this.isMenuOpen;
		},
		route(name, category) {
			this.toggleSideMenu();
			this.$router.push({ name, params: category ? { category } : undefined });
		}
	}
}
export default vm;
</script>

<style lang="scss" scoped>

.hamburger-container {
	position: absolute;
	right: 0;
	top: 0;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	width: 60px;
	height: 100%;
	z-index: 10;
	cursor: pointer;
}

.hamburger {
	height: 32px;
	position: relative;
}

.hamburger span {
	display: block;
	width: 30px;
	height: 2px;
	border-radius: 5px;
	background-color: white;
	opacity: 1;
	transition: opacity 200ms linear;

	&:not(:nth-child(3)) {
		margin-bottom: 5px;
	}
}

.hamburger p {
	position: absolute;
	text-align: center;
	margin: 0;
	font-size: 12px;
	color: white;
	bottom: 0;
	transition:
	opacity 200ms linear;

	&.close {
		opacity: 0;
	}

	&.menu {
		opacity: 1;
	}
}

.hamburger.opened span {
	background-color: black;
}

.hamburger span:first-child,
.hamburger span:nth-child(3),
.hambuger.opened span:first-child,
.hambuger.opened span:nth-child(3) {
	position: relative;
	transition: all 200ms linear;
}

.hamburger span:first-child,
.hamburger span:nth-child(3) {
	transform: rotate(0);
	top: 0;
}

.hamburger.opened span:first-child {
	transform: rotate(135deg);
	top: 4px;
}

.hamburger.opened span:nth-child(2) {
	transition: opacity 200ms linear;
	opacity: 0;
}

.hamburger.opened span:nth-child(3) {
	transform: rotate(-135deg);
	top: -10px;
}

.hamburger.opened p {
	transition: opacity 200ms linear;
	color: black;

	&.menu {
		opacity: 0;
	}

	&.close {
		opacity: 1;
	}
}

.side-menu,
.logo,
.logo-container,
.links ul,
.links ul li,
.footer {
	display: grid;
}

.side-menu {
	position: fixed;
	top: 0;
	// background-color: white;
	background: linear-gradient(to right, #efefef, #fff);
	width: 90%;
	max-width: 360px;
	height: 100%;
	grid-template-rows: 60px 150px auto 60px;
	transition: right 300ms linear;

	&.closed {
		right: -360px;
		transition: right 300ms linear;
	}

	&.opened {
		transition: right 300ms linear;
		right: 0;
		overflow: auto;
	}
}

.logo,
.logo-container {
	justify-content: center;
	align-items: center;
}

.logo {
	position: relative;
	opacity: 0;
	top: -20px;
	transition: all 200ms linear;
	transition-delay: 300ms;
}

.logo-container {
	height: 150px;
	min-width: 150px;
	background-color: white;
	border-radius: 50%;
	border: 2px solid black;
}

.side-menu.opened .logo {
	opacity: 1;
	top: 0;
	// transition-delay: 0;
}

.links {
	// background-color: red;
	padding: 20px 0;
}

.links ul {
	height: 100%;
	list-style: none;
	text-align: center;
	margin: 0;
	padding: 0;
}

.links ul li {
	height: 60px;
	// align-content: center;
	opacity: 0;
	bottom: -20px;
	position: relative;
	transition: all 200ms linear;

	&:first-child {
		transition-delay: 300ms;
	}

	&:nth-child(2) {
		transition-delay: 350ms;
	}

	&:nth-child(3) {
		transition-delay: 400ms;
	}
	&:nth-child(4) {
		transition-delay: 450ms;
	}
	&:nth-child(5) {
		transition-delay: 500ms;
	}
}

.links a {
	position: relative;
	display: flex;
	align-items: center;
	text-decoration: none;
	color: black;
	outline: none;
	transition: all 150ms linear;
	font-size: 16px;
	right: 0;
	width: auto;
	height: 100%;
	margin: 0 auto;

	&::before,
	&::after {
		content: '';
		position: relative;
		// top: 30px;
		width: 0;
		height: 0;
		border: 1px solid black;
		opacity: 0;
		transition: all 150ms linear;
		display: flex;
		align-items: center;
	}

	&::before {
		left: -10px;
	}

	&::after {
		right: -10px;
	}

	&:hover,
	&.router-link-exact-active {
		// right: 20px;
		font-size: 18px;
		font-weight: bold;
		// margin: -1px auto -1px;

		&::before,
		&::after {
			width: 25px;
			opacity: 1;
		}

		&::before {
			// left: calc(100% + 10px);
			left: calc(100% - 20px);
		}

		&::after {
			// right: calc(100% + 10px);
			right: calc(100% - 20px);
		}
	}

	&:hover {
		// right: 20px;

		&::before {
			// opacity: 1;
			// width: 25px;
			// left: calc(100% + 10px);
		}
	}


	&.router-link-exact-active {
		color: #ffc107;
		cursor: default;

		&::before,
		&::after {
			border-color: #ffc107
		}
	}
}

.side-menu.opened .links li {
	bottom: 0;
	opacity: 1;
	// transition: all 150ms linear 300ms
}

.footer {
	align-content: end;
}

.follow-us {
	position: relative;
	left: -20px;
	opacity: 0;
	transition: all 200ms linear 550ms;
	margin: 0;
}

.side-menu.opened .follow-us {
	left: 0;
	opacity: 1;
}

.icons {
	display: flex;
	justify-content: center;
	margin-top: 5px;
	margin-bottom: 20px;
}

.icons .icon {
	position: relative;
	right: -20px;
	opacity: 0;
	height: 30px;
	width: auto;
	// border: 2px solid black;
	// border-radius: 50%;
	display: inline-block;
	transition: all 200ms linear;

	&:first-child {
		transition-delay: 500ms;
	}

	&:nth-child(2) {
		transition-delay: 600ms;
	}

	&:last-child {
		transition-delay: 700ms;
	}

	&:not(:last-child) {
		margin-right: 10px;
	}

	img {
		max-width: 100%;
		max-height: 100%;
	}
}

.side-menu.opened .icons .icon {
	right: 0;
	opacity: 1;
}
</style>

