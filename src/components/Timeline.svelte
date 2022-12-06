<!-- https://codepen.io/Fischaela/pen/NWNQKW -->
<script>
	let past_jobs = [
		{
			date: "September 2022",
			title: "Full Stack Developer & Architect",
			employer: "MainLineMusic.live (MLM LLC)",
			body: [
				"Job Description: Yabba dabba doo Yabba dabba doo Yabba dabba doo Yabba dabba doo Yabba dabba doo ",
				"(Extra space)",
			],
			bullets: ["One", "Two", "Three"],
		},
		{
			date: "Summer 2021",
			title: "CIT",
			employer: "theCoderSchool Berkeley",
			body: [
				"Job Description: Yabba dabba doo Yabba dabba doo Yabba dabba doo Yabba dabba doo Yabba dabba doo ",
				"(Extra space)",
			],
			bullets: ["One", "Two", "Three"],
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
					<h3>{job.title}</h3>
					<h4>{job.employer}</h4>

					{#each job.body as chunk}
						<p>
							{chunk}
						</p>
					{/each}

					<ul>
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
		max-width: 46em;
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
