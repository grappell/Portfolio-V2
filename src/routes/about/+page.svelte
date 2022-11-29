<script>
	import anime from "animejs";
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";

	import { transitionManager } from "../../lib/store";
	import Timeline from "../../components/Timeline.svelte";

	let isOnTour = false;

	let sections = [
		{
			title: "For work:",
			body: "Here is a brief description of me, but in a way an employer would be interested",
		},
		{
			title: "On a more personal note:",
			body: "Here is a brief description of me, but like actually me",
		},
	];

	onMount(() => {
		isOnTour = $transitionManager.transitionAbout;

		anime({
			targets: ".fade-in",
			opacity: 1,
			duration: 1100,
			easing: "linear",
			delay: anime.stagger(80, {
				start: 800,
			}),
		});

		anime({
			targets: "h2 > div > hr",
			width: "100%",
			// easing: "easeOutCubic",
			easing: "easeInOutQuint",
			// easing: "easeInOutCirc",
			duration: anime.stagger(500, { start: 4000 }),
		});
	});

	function handleChange() {
		console.log("clicked");
		anime({
			targets: ".fade-in",
			opacity: 0,
			duration: 200,
			easing: "linear",
			delay: anime.stagger(100, {
				// start: 10,
			}),
			complete: () => {
				transitionManager.update((data) => {
					return { ...data, transitionAbout: true };
				});

				setTimeout(() => {
					goto("/about");
				}, 2000);
			},
		});
	}
</script>

<div
	class=" text-orange-100 w-full min-h-full flex flex-row justify-center relative overflow-x-hidden"
	id="root-div"
>
	<div class="px-5 min-h-[100vh] max-w-lg md:max-w-[100ch] pr-10 min-w-[100vmin]" id="content">
		<p class="md:text-7xl text-5xl md:mt-40 mt-20 uppercase font-bold fade-in ml-2">
			<span class="text-gray-400 text-7xl md:text-8xl font-bold font-mono">/</span>About
		</p>
		<p class="fade-in ml-2 text-red-700 py-2 pb-0 uppercase">Who Am I?</p>

		<hr class="fade-in my-5 md:mt-4 mt-3 md:w-1/2 border-orange-100" />

		<h2 class="my-7 text-3xl font-semibold max-w-fit p-5 fade-in">
			{#each sections as section}
				<div class="fade-in max-w-max">
					{section.title}
					<hr class="fade-in border-orange-100" />
				</div>
				<p
					class="text-sm md:text-base my-5 ml-1 fade-in bg-gray-800 rounded-lg p-5 font-thin max-w-[99%]"
				>
					{section.body}
				</p>
			{/each}

			<div id="timeline" class="mt-20 ">
				<div class="fade-in max-w-max">
					Work History:
					<hr class="fade-in border-orange-100" />
				</div>
				<div class="fade-in">
					<Timeline />
				</div>
			</div>

			<div class="spacer w-1 h-24 invisible" />
		</h2>
	</div>
</div>

<style>
	@import url("https://fonts.googleapis.com/css2?family=Spline+Sans+Mono:wght@500&display=swap");

	#root-div {
		background-color: rgb(20, 20, 20);
		font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
	}

	.fade-in {
		opacity: 0;
	}

	h2 > div > hr {
		width: 0;
	}

	/* .paragraph {
		padding: 10px 0;
		margin-left: 0.5rem;
	} */
</style>
