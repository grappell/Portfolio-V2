<script>
	import anime from "animejs";
	import { onMount } from "svelte";
	import ProjectCard from "../../components/Project.svelte";
	import { goto } from "$app/navigation";

	import { transitionManager } from "../../lib/store";

	// TODO: Make a longer description for this site

	const projects = [
		{
			title: "MainLineMusic",
			description:
				"A full stack web app written in Next.js, using Turborepo as a monorepo, Stripe for payment, and Firebase as the main database to build a interactive online experience that leaves new and returning users's jaws on the floor.",
			technologies: ["Next.js", "React", "Firebase", "Turborepo", "Stripe", "Supabase"],
			img: "MLM-Logo.jpg",
			externalLink: "https://mainlinemusic.live",
		},
		{
			title: "Portfolio Site",
			description: "Wow, you don't say?",
			technologies: ["Sveltekit", "Tailwind", "Anime.js", "Vercel", "Vite"],
			img: "portfolioLanding.png",
			externalLink: "/",
			gitLink: "https://github.com/grappell/Portfolio-V2",
		},
		// {
		// 	title: "Project",
		// 	description:
		// 		"Aliquip anim id ut adipisicing aliqua. Cillum magna occaecat aliqua non excepteur consequat amet aliqua nulla qui. Nulla dolor consectetur quis sint excepteur fugiat commodo velit ad",
		// 	technologies: ["JS", "Next.js", "React", "Redux"],
		// 	img: "",
		// 	externalLink: "/",
		// 	gitLink: "/",
		// },
	];

	let isOnTour = true;

	onMount(() => {
		isOnTour = $transitionManager.transitionAbout;
		// isOnTour = true;
		console.log(isOnTour, $transitionManager.transitionAbout);

		if (isOnTour) {
			anime({
				targets: "#root-div",
				backgroundColor: "rgb(20, 20, 20)",
				// delay: 500,
				duration: 500,
				easing: "linear",
			});

			transitionManager.update((current) => {
				return { ...current, transitionAbout: false };
			});
		} else {
			document.getElementById("root-div").style.backgroundColor = "rgb(20, 20, 20)";
		}

		anime({
			targets: ".fade-in",
			opacity: 1,
			duration: 1100,
			easing: "linear",
			delay: anime.stagger(80, {
				start: 800,
			}),
			// complete: () => {
			// 	if (!isOnTour) return;
			// 	document.getElementById("cont-button").style.opacity = 1;
			// },
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
					return { ...data, transitionAbout: false };
				});

				scrollTo({
					top: 0,
					left: 0,
					behavior: "smooth",
				});

				setTimeout(() => {
					goto("/about");
				}, 100);
			},
		});
	}
</script>

<div
	class=" text-orange-100 w-full min-h-full flex flex-row justify-center relative overflow-x-hidden"
	id="root-div"
>
	<div class="px-5 h-[100vh] max-w-lg md:max-w-[160ch] pr-10 min-w-[100vmin]" id="content">
		<p class="md:text-7xl text-5xl md:mt-40 mt-20 uppercase font-bold fade-in ml-2">
			<span class="text-gray-400 text-7xl md:text-8xl font-bold font-mono">/</span>Projects
		</p>
		<p class="fade-in ml-2 text-red-700 py-2 pb-0 uppercase">Stuff i've made</p>

		<hr class="fade-in my-5 md:mt-4 mt-3 md:w-1/2 border-orange-100" />

		{#each projects as project}
			<span class="fade-in">
				<ProjectCard props={project} />
			</span>
		{/each}

		{#if isOnTour}
			<div class="flex flex-row justify-center md:mt-20 mt-10 ml-6">
				<button
					id="cont-button"
					class=" bg-red-800 px-10 py-4 rounded-lg hover:bg-red-300 transition-colors hover:text-black text-2xl fade-in"
					on:click={handleChange}
				>
					Continue
				</button>
			</div>
		{/if}

		<div class="spacer w-screen h-24 invisible" />
	</div>
</div>

<style>
	@import url("https://fonts.googleapis.com/css2?family=Spline+Sans+Mono:wght@500&display=swap");

	#root-div {
		background-color: rgb(175, 40, 40);
		font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
	}

	.fade-in {
		opacity: 0;
	}

	/* #cont-button {
		transition: opacity 150ms, color 150ms, background 150ms;
	} */

	/* .paragraph {
		padding: 10px 0;
		margin-left: 0.5rem;
	} */
</style>
