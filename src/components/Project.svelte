<script>
	import { onMount } from 'svelte';
	import ExternalLinkSvg from './ExternalLinkSVG.svelte';
	import GitHubSvg from './GitHubSVG.svelte';

	export let props = {
		title: 'Project',
		description:
			'Aliquip anim id ut adipisicing aliqua. Cillum magna occaecat aliqua non excepteur consequat amet aliqua nulla qui. Nulla dolor consectetur quis sint excepteur fugiat commodo velit ad',
		technologies: []
	};

	onMount(() => {});
</script>

<div class="flex flex-col justify-center mr-10 w-full p-2 ">
	<div
		id="wrapper"
		class="my-2 bg-gray-800 relative grid md:grid-cols-2 grid-cols-1 p-6 rounded-lg w-full gap-7 shadow-xl"
	>
		<div id="img" class="hidden md:block">
			<div
				class="h-72 w-full bg-cent rounded-xl"
				style={`Background: url('${
					props.img
						? props.img
						: 'https://www.technistone.com/color-range/image-slab/Noble%20Concrete%20Grey_SLAB_web2.jpg'
				}'); background-size: cover; background-repeat: no-repeat; background-position: center;`}
			/>
		</div>
		<div class="text-wrapper">
			<div class="ctx-title text-orange-400 font-thin">Featured Project</div>
			<div class="title font-semibold text-4xl mt-3 mb-4">{props.title}</div>
			<div
				class="tools text-gray-400 text-center overflow-clip flex flex-row flex-wrap justify-start mb-6"
			>
				{#each props.technologies as technologies}
					<div class="space">{technologies}</div>
				{/each}
			</div>
			<div class="desc mb-5 text-l border rounded-lg p-5 border-gray-600">
				{props.description}
			</div>
			<div class="links flex flex-row justify-center gap-20">
				{#if props.externalLink}
					<a
						class="hover:cursor-pointer"
						target="_blank"
						rel="noreferrer noopener"
						href={props.externalLink}
					>
						<ExternalLinkSvg />
					</a>
				{/if}
				{#if props.gitLink}
					<a
						class="hover:cursor-pointer"
						target="_blank"
						rel="noreferrer noopener"
						href={props.gitLink}
					>
						<GitHubSvg />
					</a>
				{/if}
			</div>
		</div>
	</div>
</div>

<style>
	.space {
		margin-right: 10px;
		/* text-decoration: underline; */
	}
</style>
