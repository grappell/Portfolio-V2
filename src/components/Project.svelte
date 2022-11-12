<script>
	import { onMount } from "svelte";
	import ExternalLinkSvg from "./ExternalLinkSVG.svelte";
	import GitHubSvg from "./GitHubSVG.svelte";
	import { kebabCase } from "lodash";

	export let props = {};

	onMount(() => {});
</script>

<div class="flex flex-col justify-center ml-0 w-[90vw] sm:w-full mr-10 p-2">
	<div
		id="wrapper"
		class="my-2 bg-gray-800 relative grid md:grid-cols-2 grid-cols-1 p-6 rounded-lg w-full gap-7 shadow-xl hover:scale-[101%] transition-transform"
	>
		<a
			href={`/projects/${kebabCase(props.title)}`}
			class="text-inherit hover:text-inherit cursor-pointer md:block hidden"
		>
			<div id="img">
				<div
					class="md:h-72 h-32 w-full bg-cent rounded-xl"
					style={`Background: url('${
						props.img
							? props.img
							: "https://www.technistone.com/color-range/image-slab/Noble%20Concrete%20Grey_SLAB_web2.jpg"
					}'); background-size: cover; background-repeat: no-repeat; background-position: center;`}
				/>
			</div>
		</a>

		<div class="text-wrapper">
			<div class="ctx-title text-orange-400 font-thin">Featured Project</div>
			<div class="title font-semibold text-4xl mt-3 mb-4">{props.title}</div>
			<a
				href={`/projects/${kebabCase(props.title)}`}
				class="text-inherit hover:text-inherit cursor-pointer block md:hidden mb-5"
			>
				<div id="img">
					<div
						class="md:h-72 h-32 w-full bg-cent rounded-xl"
						style={`Background: url('${
							props.img
								? props.img
								: "https://www.technistone.com/color-range/image-slab/Noble%20Concrete%20Grey_SLAB_web2.jpg"
						}'); background-size: cover; background-repeat: no-repeat; background-position: center;`}
					/>
				</div>
			</a>

			<div
				class="tools text-gray-400 text-center overflow-clip flex flex-row flex-wrap justify-start mb-6"
			>
				{#each props.technologies as technologies}
					<div class="space">{technologies}</div>
				{/each}
			</div>
			<hr class="mb-5 border-orange-100" />
			<div class="desc mb-5 text-l px-2 rounded-lg border-gray-600">
				{props.description}
			</div>
			<div
				class="links flex flex-col justify-center gap-5 absolute -top-3 -right-3 bg-gray-800 p-2 rounded-xl border border-gray-600"
			>
				{#if props.externalLink}
					<a
						class="hover:cursor-pointer hover:text-blue-100 text-orange-500"
						target="_blank"
						rel="noreferrer noopener"
						href={props.externalLink}
					>
						<ExternalLinkSvg />
					</a>
				{/if}
				{#if props.gitLink}
					<a
						class="hover:cursor-pointer hover:text-blue-100 text-orange-500"
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
