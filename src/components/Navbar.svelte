<script>
	import { onMount } from 'svelte';

	let checkbox;

	const hideMenu = () => {
		// console.log('disabled');
		checkbox.checked = false;
	};

	onMount(function () {
		checkbox = document.getElementById('active');

		var aTags = document.getElementsByClassName('menu-a');

		Array.from(aTags).forEach((element) => {
			element.addEventListener('click', (e) => {
				let checkbox = document.getElementById('active');
				checkbox.checked = false;
			});
		});

		// const menu = document.getElementById('menu');

		// Array.from(document.getElementsByClassName('menu-item')).forEach((item, index) => {
		// 	item.onmouseover = () => {
		// 		menu.dataset.activeIndex = index;
		// 	};
		// });
	});
</script>

<head>
	<link href="https://fonts.googleapis.com/css2?family=Oswald&display=swap" rel="stylesheet" />
	<link href="https://fonts.googleapis.com/css2?family=Lato&display=swap" rel="stylesheet" />
	<script src="https://kit.fontawesome.com/a076d05399.js"></script>
</head>

<!-- <a href="/">
		<div id="logo">Studio Wifi</div>
	</a> -->
<input type="checkbox" id="active" />
<label for="active" class="menu-btn"><span /></label>
<label for="active" class="close" />
<div class="wrapper">
	<!-- <ul>
		<li><a class="menu-a" href="/#">Home</a></li>
		<li><a class="menu-a" href="/#about-me">About</a></li>
		<li><a class="menu-a" href="/#projects">Projects</a></li>
		<li><a class="menu-a" href="/#my-tools">Tools</a></li>
		<li><a class="menu-a" href="/#contacts">Contact</a></li>
		<li><a class="menu-a" href="/resume">Resume</a></li>
	</ul> -->
	<div id="menu">
		<div id="menu-items">
			<!-- I made these divs instead of links so you can click on mobile to view the effect -->
			<a href="/" on:click={hideMenu} class="menu-item">Home</a>
			<a href="/projects" on:click={hideMenu} class="menu-item">Projects</a>
			<a href="/about" on:click={hideMenu} class="menu-item">About</a>
			<a href="/#" on:click={hideMenu} class="menu-item">Resume</a>
			<a href="/#" on:click={hideMenu} class="menu-item">Contact</a>
		</div>
		<div id="menu-background-pattern" data-active-index="0" />
		<div id="menu-background-image" />
	</div>
</div>

<style>
	/* #logo {
		border-radius: 10px;
		font-size: 25px;
		padding: 9px;
		padding-left: 35px;
		padding-right: 35px;
		font-weight: 600;
		background-color: rgb(175, 40, 40);
		position: fixed;
		z-index: 700;
		left: 20px;
		top: 20px;
		text-align: center;
	}

	#logo:hover {
		background-color: rgb(104, 24, 24);
		color: white;
		cursor: pointer;
	} */

	a {
		text-decoration: none;
		margin: 0;
		color: inherit;
	}

	#menu {
		align-items: center;
		display: flex;
		height: 100vh;
		width: 100vw;
	}

	#menu-items {
		margin-left: clamp(4rem, 20vw, 48rem);
		position: relative;
		z-index: 2;
	}
	/* 
	#menu[data-active-index='0'] > #menu-background-pattern {
		background-position: 0% -25%;
	}

	#menu[data-active-index='1'] > #menu-background-pattern {
		background-position: 0% -50%;
	}

	#menu[data-active-index='2'] > #menu-background-pattern {
		background-position: 0% -75%;
	}

	#menu[data-active-index='3'] > #menu-background-pattern {
		background-position: 0% -100%;
	}

	#menu[data-active-index='0'] > #menu-background-image {
		background-position: center 45%;
	}

	#menu[data-active-index='1'] > #menu-background-image {
		background-position: center 50%;
	}

	#menu[data-active-index='2'] > #menu-background-image {
		background-position: center 55%;
	}

	#menu[data-active-index='3'] > #menu-background-image {
		background-position: center 60%;
	} */

	#menu-background-pattern {
		background-image: radial-gradient(rgba(255, 255, 255, 0.1) 9%, transparent 9%);
		background-position: 0% 0%;
		background-size: 12vmin 12vmin;
		height: 100vh;
		left: 0px;
		position: absolute;
		top: 0px;
		transition: opacity 800ms ease, background-size 800ms ease, background-position 800ms ease;
		width: 100vw;
		z-index: 1;
	}

	#menu-background-image {
		/* background-image: url('https://images.unsplash.com/photo-1604964432806-254d07c11f32?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80'); */
		/* background-image: url('https://images.unsplash.com/photo-1547157720-52d782e55b83?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80'); */
		background-image: url('https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80');
		background-position: center 40%;
		background-size: 110vmax;
		height: 100%;
		left: 0px;
		opacity: 0.15;
		position: absolute;
		top: 0px;
		transition: opacity 800ms ease, background-size 800ms ease, background-position 800ms ease;
		width: 100%;
		z-index: 0;
	}

	#menu-items:hover ~ #menu-background-pattern {
		background-size: 11vmin 11vmin;
		opacity: 0.5;
	}

	#menu-items:hover ~ #menu-background-image {
		background-size: 100vmax;
		opacity: 0.1;
	}

	#menu-items:hover > .menu-item {
		opacity: 0.3;
	}

	#menu-items:hover > .menu-item:hover {
		opacity: 1;
	}

	.menu-item {
		color: white;
		cursor: pointer;
		display: block;
		font-size: clamp(3rem, 8vw, 6rem);
		padding: clamp(0.25rem, 0.5vw, 1rem) 0rem;
		text-decoration: none;
		transition: opacity 400ms ease;
	}

	/* ----------------------------------------------------------------------------------------- */

	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: 'Lato', sans-serif;
		font-family: 'Oswald', sans-serif;
	}

	.wrapper {
		position: fixed;
		top: 0;
		/* left: -100%; */
		right: -100%;
		height: 100%;
		width: 100%;
		/* background: linear-gradient(90deg, #f92c78, #4114a1); */
		/* background: linear-gradient(375deg, #1cc7d0, #2ede98); */
		/* background: linear-gradient(-45deg, #e3eefe 0%, #efddfb 100%); */
		background: rgb(20, 20, 20);
		/* background: url('../test-flipped.svg') no-repeat right center / cover, rgb(123, 137, 141); */

		transition: all 0.5s ease-in-out;

		z-index: 500;
	}
	#active:checked ~ .wrapper {
		/* left: 0; */
		right: 0;
	}
	.menu-btn {
		position: fixed;
		z-index: 700;
		right: 20px;
		/*left: 20px; */
		top: 20px;
		height: 55px;
		width: 55px;
		text-align: center;
		line-height: 50px;
		border-radius: 50%;
		font-size: 20px;
		cursor: pointer;
		color: #fff;
		background-color: rgb(175, 40, 40);
		/* background: linear-gradient(90deg, #f92c78, #4114a1); */
		/* background: linear-gradient(375deg, #1cc7d0, #2ede98); */
		/* background: linear-gradient(-45deg, #e3eefe 0%, #efddfb 100%); */
		transition: all 0.3s ease-in-out;
	}
	.menu-btn span,
	.menu-btn:before,
	.menu-btn:after {
		content: '';
		position: absolute;
		top: calc(50% - 1px);
		left: 30%;
		width: 40%;
		border-bottom: 2px solid #000;
		transition: transform 0.3s cubic-bezier(0.215, 0.61, 0.355, 1);
	}
	.menu-btn:before {
		transform: translateY(-8px);
	}
	.menu-btn:after {
		transform: translateY(8px);
	}

	.close {
		z-index: 700;
		width: 100%;
		height: 100%;
		pointer-events: none;
		transition: background 0.6s;
	}

	/* closing animation */
	#active:checked + .menu-btn span {
		transform: scaleX(0);
	}
	#active:checked + .menu-btn:before {
		transform: rotate(45deg);
		border-color: #fff;
	}
	#active:checked + .menu-btn:after {
		transform: rotate(-45deg);
		border-color: #fff;
	}

	input[type='checkbox'] {
		display: none;
	}
</style>
