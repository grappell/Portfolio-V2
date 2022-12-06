<!-- https://codepen.io/Fischaela/pen/NWNQKW -->
<script>
	let past_jobs = [
		{
			date: "August 2022 to Present",
			title: "Full Stack Developer & Architect",
			employer: "MainLineMusic.live (MLM LLC)",
			body: [
				"MainLineMusic is a tech firm that specializes connecting you (as the fan) to your favorite musicians. I was hired as the only developer, where I was responsible for everything that had to do with technology. I was at times the IT guy, database admin, software architect, and so much more. I took the challenge of creating a full stack app, capable of scaling to millions, to heart.",
				"During my time at MainLineMusic, I was closely involved with every single step of creation, from design to working product. When I started, the idea was only a brainstorm, and over the next year, it evolved into the thing that is today.",
			],
			bullets: [
				"Maintained a complete codebase, from server to website",
				"Took on many roles, not just ones of a developer",
				"Contributed to the positive growth of the company through innovative ideas",
			],
		},
		{
			date: "Summer 2021",
			title: "CIT",
			employer: "TheCoderSchool Berkeley",
			body: [
				"TheCoderSchool is a company that focuses on teaching kids how to code. During my quick summer there as a CIT, I helped teach around 30 kids the ins and outs of how to build websites. We covered everything from how to create simple websites to making complex logic for stylized, custom sites",
			],
			bullets: [
				"Fostered a deep and rich learning environment for students",
				"Aided counselors in their jobs to further productivity",
			],
		},
	];
</script>

<div id="body">
	<ul class="timeline">
		{#each past_jobs as job}
			<li class="timeline-event">
				<!-- svelte-ignore a11y-label-has-associated-control -->
				<label class="timeline-event-icon" />
				<div class="timeline-event-copy">
					<p class="timeline-event-thumbnail">{job.date}</p>
					<h3 class="text-orange-300">{job.title}</h3>
					<h4>@ {job.employer}</h4>

					{#each job.body as chunk}
						<p class="text-sm">
							{chunk}
						</p>
					{/each}

					<div class="bg-gray-800 bg-opacity-30 p-5 rounded-lg mt-4">
						<p class="text-lg text-orange-200">Quick highlights:</p>
						<ul class="-mt-5 text-sm">
							{#each job.bullets as bullet}
								<li>
									<span class="text-2xl -my-5">&rarrc;</span>
									<!-- Add the arrow in front of the entry -->
									<!-- <span class="text-2xl -my-5">&rarrhk;</span> (Possible alternative) -->
									{bullet}
								</li>
							{/each}
						</ul>
					</div>
				</div>
			</li>
		{/each}
	</ul>
</div>

<style>
	/* Fonts */
	@import url("https://fonts.googleapis.com/css?family=Open+Sans:300,700");
	#body {
		font-size: 0.5em;
		font-weight: 300;
		line-height: 1.5;
		letter-spacing: 0.05em;
	}

	/* Layout */
	* {
		-moz-box-sizing: border-box;
		-webkit-box-sizing: border-box;
		box-sizing: border-box;
	}

	/* Styling */
	.timeline {
		margin: 4em auto;
		position: relative;
		/* max-width: 46em; */
		max-width: 100%;
	}
	.timeline:before {
		background-image: linear-gradient(to bottom, rgba(134, 129, 123, 1), rgba(134, 129, 123, 0));
		/* background-color: rgba(134, 129, 123, 1); */
		content: "";
		margin-left: -1px;
		position: absolute;
		top: 0;
		left: 2em;
		width: 2px;
		height: 100%;
		border-radius: 100px;
	}

	.timeline-event {
		position: relative;
	}
	.timeline-event:hover .timeline-event-icon {
		-moz-transform: rotate(-45deg);
		-ms-transform: rotate(-45deg);
		-webkit-transform: rotate(-45deg);
		transform: rotate(-45deg);
		background-color: #a70000;
	}
	.timeline-event:hover .timeline-event-thumbnail {
		-moz-box-shadow: inset 40em 0 0 0 rgb(146, 70, 16);
		-webkit-box-shadow: inset 40em 0 0 0 rgb(146, 70, 16);
		box-shadow: inset 40em 0 0 0 rgb(146, 70, 16);
	}

	.timeline-event-copy {
		padding: 2em;
		position: relative;
		top: -1.875em;
		left: 4em;
		width: 80%;
	}
	.timeline-event-copy h3 {
		font-size: 1.75em;
	}
	.timeline-event-copy h4 {
		font-size: 1.2em;
		margin-bottom: 1.2em;
	}

	.timeline-event-copy p:not(.timeline-event-thumbnail) {
		padding-bottom: 1.2em;
	}

	.timeline-event-icon {
		-moz-transition: -moz-transform 0.2s ease-in;
		-o-transition: -o-transform 0.2s ease-in;
		-webkit-transition: -webkit-transform 0.2s ease-in;
		transition: transform 0.2s ease-in;
		-moz-transform: rotate(45deg);
		-ms-transform: rotate(45deg);
		-webkit-transform: rotate(45deg);
		transform: rotate(45deg);
		background-color: black;
		outline: 10px solid white;
		display: block;
		margin: 0.5em 0.5em 0.5em -0.5em;
		position: absolute;
		top: 0;
		left: 2em;
		width: 1em;
		height: 1em;
	}

	.timeline-event-thumbnail {
		-moz-transition: box-shadow 0.5s ease-in 0.1s;
		-o-transition: box-shadow 0.5s ease-in 0.1s;
		-webkit-transition: box-shadow 0.5s ease-in;
		-webkit-transition-delay: 0.1s;
		transition-delay: 0.1s;
		transition: box-shadow 0.5s ease-in 0.1s;
		color: white;
		font-size: 0.75em;
		background-color: black;
		-moz-box-shadow: inset 0 0 0 0em #ef795a;
		-webkit-box-shadow: inset 0 0 0 0em #ef795a;
		box-shadow: inset 0 0 0 0em #ef795a;
		display: inline-block;
		margin-bottom: 1.2em;
		padding: 0.25em 1em 0.2em 1em;
	}
</style>
