<template>
  <div class="home">
		<div class="hero">
			<div class="logo">
				hey autumn
			</div>
			<div class="post-title">
				<h1>Making cool stuff 101</h1>
			</div>
			<div class="post-description">
				<p>Want to make cool stuff? This is the place to learn how...</p>
			</div>
		</div>
		<div class="featured">
			<div class="post">
				<h2>Featured Post Title</h2>
			</div>
			<div class="post">
				<h2>Featured Post Title</h2>
			</div>
		</div>
		<div class="recent-posts">
			<div class="posts-container">
				<div class="recent-post">
					<h3>Recent Post Title 1</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
					<div class="read-more">
						<button>Read More</button>
					</div>
				</div>
				<div class="recent-post">
					<h3>Recent Post Title 2</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
					<div class="read-more">
						<button>Read More</button>
					</div>
				</div>
				<div class="recent-post">
					<h3>Recent Post Title 3</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
					<div class="read-more">
						<button>Read More</button>
					</div>
				</div>
				<div class="recent-post">
					<h3>Recent Post Title 4</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
					<div class="read-more">
						<button>Read More</button>
					</div>
				</div>
				<div class="recent-post">
					<h3>Recent Post Title 5</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
					<div class="read-more">
						<button>Read More</button>
					</div>
				</div>
				<div class="recent-post">
					<h3>Recent Post Title 6</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
					<div class="read-more">
						<button>Read More</button>
					</div>
				</div>
			</div>
			<div class="all-posts">
				<button>All Posts</button>
			</div>
		</div>
		<div class="about">
			<div class="image-container">
				<div class="image"></div>
			</div>
			<p class="blurb">Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum ab, delectus commodi qui cupiditate unde dolore, quod corrupti minima deserunt consectetur neque accusamus. Quia excepturi illum facere magnam officia sed?</p>
			<button>Read More</button>
		</div>
  </div>
</template>

<script>


export default {
	name: 'home',
	components: {
		
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

.home,
.featured,
.featured .post {
	display: grid;
}

.home {
	grid-template-rows: 310px 175px auto auto;
}

.hero,
.featured .post {
	cursor: pointer;
}

.hero,
.recent-posts {
	background-color: #ffc107;
}

.hero {
	background:
		linear-gradient(rgba(0, 0, 0, .75), rgba(0, 0, 0, .75)),
		url('https://static.pexels.com/photos/54455/cook-food-kitchen-eat-54455.jpeg');
	background-size: cover;
	background-position: center 100%;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	text-align: center;
}

.hero .logo {
	height: 75px;
	width: 60%;
	margin: 40px auto 20px;
	border: 2px solid white;
	color: white;
	display: flex;
	justify-content: center;
	align-items: center;
}

.hero h1,
.hero p {
	margin: 0;
	color: white;
}

.featured {
	grid-template-columns: repeat(2, 50%);
}

.featured .post {
	height: 100%;
	align-items: center;
}

.featured .post:first-child {
	border-right: 1px solid black;
}

.recent-posts {
	display: grid;
	grid-template-rows: repeat(2, auto);
	/* grid-template-rows: repeat(5, auto); */
	/* grid-template-rows: repeat(3, auto); */
	/* grid-template-columns: repeat(2, 50%); */
}

.posts-container {
	display: grid;
	grid-template-rows: repeat(6, auto);

	@media (min-width: 720px) {	
		grid-template-rows: repeat(2, auto);
		grid-template-columns: repeat(3, 1fr);
	}
}

.recent-post {
	padding: 0 30px;
	cursor: pointer;

	@media screen and (min-width: 720px) {
		&:first-child,
		&:nth-child(2),
		&:nth-child(4),
		&:nth-child(5) {
			border-right: 2px solid white;
		}

		&:first-child,
		&:nth-child(2),
		&:nth-child(3) {
			border-bottom: 2px solid white;
		}
	}

}

.recent-post h3 {
	margin-bottom: 20px;
}

.recent-post p {
	text-align: center;
}

.recent-post .read-more {
	/* margin-bottom: 20px; */
	padding-bottom: 20px;
	border-bottom: 2px solid white;

	@media screen and (min-width: 720px) {
		border: none;
	}
}

.recent-post .read-more button {
	border: 2px solid black;
	color: black;
	border-radius: 0;
	background-color: transparent;
}

.all-posts {
	padding: 20px 0;
	// background-color: white;
	border-bottom: 2px solid black;

	@media screen and (min-width: 720px) {
		border-top: 2px solid white;		
	}
}

.all-posts button {
	background-color: transparent;
	color: white;
	border: 2px solid white;
	border-radius: 0;
}

.about {
	padding: 20px 30px;
}

.about .image-container {
	width: 100px;
	height: 100px;
	border: 2px solid black;
	border-radius: 50%;
	margin: 0 auto;
}

.about .blurb {
	text-align: center;
}

</style>
