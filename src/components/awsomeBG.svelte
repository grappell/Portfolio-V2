<script>
	import { onMount } from 'svelte';
	import anime from 'animejs/lib/anime';

	import { useEffect } from '../lib/hooks';

	export let clicked = false;

	let colums;
	let rows;

	let wrapper;
	let body;

	let hasStarted = false;

	// make sure that the event only fires once
	useEffect(
		() => {
			if (hasStarted) {
				console.log('Clicked on button');
			}

			hasStarted = true;
		},
		() => [clicked]
	);

	const createTile = (index) => {
		const tile = document.createElement('div');
		tile.classList.add('tile');
		tile.style.backgroundColor = 'rgb(20, 20, 20)';

		tile.onclick = (e) => handleOnClick(index);

		return tile;
	};

	const createTiles = (quantity) => {
		Array.from(Array(quantity)).map((tile, index) => {
			wrapper.appendChild(createTile(index));
		});
	};

	const handleOnClick = (index) => {
		console.log(clicked, index);

		anime({
			targets: '.tile',
			backgroundColor: 'rgb(175, 40, 40)'
		});
	};

	const createGrid = () => {
		wrapper.innerHTML = '';

		colums = Math.floor(document.body.clientWidth / 50);
		rows = Math.floor(document.body.clientHeight / 50);

		wrapper.style.setProperty('--cols', colums);
		wrapper.style.setProperty('--rows', rows);

		createTiles(colums * rows);
	};

	onMount(() => {
		wrapper = document.getElementById('tiles');
		body = document.getElementById('body');

		colums = Math.floor(document.body.clientWidth / 50);
		rows = Math.floor(document.body.clientHeight / 50);

		createTiles(colums * rows);

		window.onresize = () => createGrid();

		createGrid();

		// This is done so that there is no mismatched bg when you first arrive
		body.style.setProperty(
			'--bg',
			'linear-gradient(to right, var(--col-1), var(--col-2), var(--col-1))'
		);
	});
</script>

<div id="body" class="w-[100%] h-[100vh] absolute top-0 left-0 -z-10">
	<div id="tiles" />
</div>

<style>
	:root {
		--col-1: rgb(71, 0, 0);
		--col-2: rgb(175, 40, 40);
	}

	#body {
		--bg: rgb(40, 40, 40);
		/* background-color: rgb(20, 20, 20); */
		/* background: linear-gradient(to right, var(--col-1), var(--col-2), var(--col-1)); */
		background: var(--bg);
		background-size: 200%;
		animation: bg-pan 7s linear infinite;
		overflow: hidden;
		margin: 0;
	}

	@keyframes bg-pan {
		from {
			background-position: 0% center;
		}
		to {
			background-position: -200% center;
		}
	}

	#tiles {
		height: 100vh;
		width: 100vw;

		display: grid;

		grid-template-columns: repeat(var(--cols), 1fr);
		grid-template-rows: repeat(var(--rows), 1fr);

		gap: 1px;
	}
</style>
