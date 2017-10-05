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
				<li><a href="#" class="menu-link selected">HOME</a></li>
				<li><a href="#" class="menu-link">FOOD</a></li>
				<li><a href="#" class="menu-link">LIFESTYLE</a></li>
				<li><a href="#" class="menu-link">TRAVEL</a></li>
				<li><a href="#" class="menu-link">ABOUT US</a></li>
			</ul>
		</div>
		<div class="footer">
			<p class="follow-us">Follow Us</p>
			<div class="icons">

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
	background-color: black;
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
	color: black;
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

.logo-container {
	height: 150px;
	min-width: 150px;
	background-color: white;
	border-radius: 50%;
	border: 2px solid black;
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
	&.selected {
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


	&.selected {
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
	margin: 0;
}

.icons {
	height: 30px;
}
</style>

