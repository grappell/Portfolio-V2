<script>
	import Background from '../components/Welcome-Background.svelte';
	import './../css/retro-buttons.css';

	let clicked;
</script>

<div class="w-full flex flex-row justify-center relative overflow-hidden" id="root-welcome">
	<Background {clicked} />
	<div class="px-5 h-[100vh] max-w-lg md:max-w-[160ch]">
		<p
			class="text-gray-400 text-6xl font-semibold text-center translate-y-[12vh] md:translate-y-[25vh] mb-10 md:mb-20 md:text-8xl titles"
		>
			Hello, my name is <span class="text-red-500">Grayson Appell</span>
		</p>
		<div
			class="text-gray-400 text-6xl font-semibold text-center translate-y-[12vh] md:translate-y-[25vh] titles"
		>
			<p>Welcome to <span class="text-red-500">Studio Wifi</span></p>
			<div class="flex-none md:mt-40 mt-20">
				<button class="retro rbtn-big" id="tour-button" on:click={() => (clicked = true)}>
					<span id="text">Take a tour</span>
				</button>
			</div>
		</div>
	</div>
</div>

<style>
</style>
