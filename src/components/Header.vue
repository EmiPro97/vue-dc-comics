<template>
	<header>
		<div class="container flex space-between a-items-center">
			<a class="img-wrap" href="#"
				><img src="../assets/img/dc-logo.png" alt="logo-dc"
			/></a>
			<nav>
				<ul class="flex">
					<li v-for="(link, index) in navLinks" :key="index">
						<a	class="text-uppercase"
							:href="link.url"
							:class="{ active: link.active }"
							@click="toggleActive(index)"
							>{{ link.text }}</a
						>
						<div class="line" :class="{ active: link.active }"></div>
					</li>
				</ul>
			</nav>
		</div>
	</header>
</template>

<script>
	export default {
		name: "Header",
		data() {
			return {
				navLinks: [
					{ text: "characters", url: "#", active: false },
					{ text: "comics", url: "#", active: true },
					{ text: "movies", url: "#", active: false },
					{ text: "tv", url: "#", active: false },
					{ text: "games", url: "#", active: false },
					{ text: "collectibles", url: "#", active: false },
					{ text: "videos", url: "#", active: false },
					{ text: "fans", url: "#", active: false },
					{ text: "news", url: "#", active: false },
					{ text: "shop", url: "#", active: false },
				],
			};
		},
		methods: {
			toggleActive(index) {
				this.navLinks.forEach((element) => {
					if (element.active === true) {
						element.active = false;
					}
				});
				this.navLinks[index].active = !this.navLinks[index].active;
			},
		},
	};
</script>

<style scoped lang="scss">
// Variables
@import '../styles/vars';

// Header fixed
header{
	position: fixed;
	width: 100%;
	top: 0;
	left: 0;
	z-index: 10;
	background: #fff;
}

/* Img */
.img-wrap {
	max-width: 70px;
	max-height: 70px;
	& img {
		width: 100%;
		height: 100%;
	}
}

/* Nav */
ul li {
	margin-right: 35px;
	line-height: 120px;
	position: relative;
	&:last-child {margin-right: 0;}
	& .line {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 0%;
		height: 5px;
		background: $dodger;
		transition: width 0.4s ease-out;
	}
	& .line.active {
		width: 100%;
	}
	& a {
		font-weight: 700;
		color: #464646;
		transition: color 0.4s;
		&.active,
		&:hover {color: $dodger;}
	}
}

</style>
