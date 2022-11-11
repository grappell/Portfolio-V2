<script>
	import anime from 'animejs';
	import { onMount } from 'svelte';

	onMount(() => {
		anime({
			targets: '#root-div',
			backgroundColor: 'rgb(20, 20, 20)',
			// delay: 500,
			duration: 500,
			easing: 'linear'
		});

		anime({
			targets: '.fade-in',
			opacity: 1,
			duration: 1000,
			easing: 'easeInQuad',
			delay: anime.stagger(100, {
				start: 800
			})
		});
	});
</script>

<div
	class=" text-orange-100 w-full min-h-full flex flex-row justify-center relative overflow-x-hidden"
	id="root-div"
>
	<div class="px-5 h-[100vh] max-w-lg md:max-w-[160ch]" id="content">
		<p class="md:text-7xl text-5xl mt-40 uppercase font-bold fade-in ml-2">About Me</p>
		<p class="fade-in ml-2 text-red-700">Grayson Appell</p>

		<hr class="fade-in my-5 md:w-1/2" />

		<p class="fade-in paragraph">
			Commodo ad proident reprehenderit consequat officia consequat in aute et deserunt commodo
			adipisicing eu fugiat. Est qui reprehenderit Lorem amet excepteur minim exercitation occaecat
			aliquip cupidatat. Culpa fugiat in nisi sit tempor ad nostrud reprehenderit fugiat Lorem
			consectetur nulla aliqua. Ea tempor in aliquip occaecat aute sint excepteur labore Lorem.
			Aliqua est ea consequat Lorem mollit ad irure. Enim ullamco sunt adipisicing fugiat laborum
			fugiat cillum nostrud proident veniam. Est velit fugiat amet id elit cupidatat exercitation eu
			esse pariatur in Lorem mollit mollit. Nostrud irure labore eu tempor consequat adipisicing
			culpa sunt anim voluptate in esse laboris. Amet esse nostrud dolor qui velit laboris voluptate
			Lorem deserunt ex aute nisi. Exercitation id nisi velit aliquip sint incididunt. Mollit aliqua
			amet ea ad cillum. Enim velit laborum sit tempor fugiat ea amet ut incididunt nulla occaecat
			in veniam sunt.
		</p>
		<p class="fade-in paragraph">
			Deserunt consectetur ex dolore eiusmod reprehenderit id. Amet exercitation non ipsum dolor
			sint ipsum nulla sit nostrud do nulla. Irure laboris cillum excepteur esse ipsum cillum in
			deserunt deserunt exercitation minim. Esse proident quis nulla sit consectetur incididunt.
			Cillum nulla eiusmod amet dolore dolore aliqua quis amet est sunt eu sunt in exercitation.
			Pariatur id labore aute in aliquip irure. Sit Lorem aliquip incididunt deserunt. Minim aute
			incididunt deserunt fugiat. Mollit sunt ex cupidatat incididunt dolor. Aute non nisi qui
			ullamco dolor et proident fugiat pariatur ex duis eiusmod sit excepteur. Qui voluptate non
			dolor amet commodo elit.
		</p>
		<p class="fade-in paragraph">
			Nulla fugiat do dolor incididunt ad. Est veniam velit sunt id. Voluptate exercitation fugiat
			velit sint voluptate ex labore non consequat reprehenderit voluptate sit. Aliqua amet et duis
			sit magna nisi minim aliquip aute tempor. Aliqua ut amet ea dolore magna quis commodo id culpa
			reprehenderit aliquip voluptate. Ea eu occaecat eiusmod culpa. Irure ut ut laborum voluptate
			reprehenderit aliqua reprehenderit ex dolor culpa non. Officia occaecat cupidatat occaecat
			culpa culpa eiusmod exercitation exercitation velit anim. Do sit ut non nostrud officia
			consectetur aliqua. Veniam id occaecat est tempor tempor veniam sunt. Fugiat nisi ipsum minim
			deserunt laborum irure id exercitation quis. Lorem nulla velit quis esse sit ex aute ut
			cillum. Esse irure culpa consectetur ea proident non ipsum proident velit. Occaecat qui in
			dolore enim. Enim ut elit labore in officia eiusmod quis quis consectetur sunt mollit ipsum
			pariatur. Id voluptate mollit veniam minim.
		</p>
		<p class="fade-in paragraph">
			Ipsum tempor esse anim laboris sunt irure velit. Id ut exercitation incididunt ut non officia
			amet nisi et. Voluptate est officia cupidatat occaecat ex nisi. Excepteur veniam sunt id
			voluptate anim Lorem. Excepteur eiusmod amet eiusmod do do dolore voluptate nisi exercitation
			ullamco veniam adipisicing amet. Duis aliqua cupidatat incididunt sunt tempor mollit amet
			labore occaecat fugiat ea do. Duis esse sunt labore velit adipisicing Lorem voluptate sunt
			voluptate. Nisi sunt exercitation cillum id excepteur. Adipisicing est exercitation aute
			exercitation ea laborum. Duis nisi non reprehenderit do dolore enim id nisi nisi dolore
			reprehenderit reprehenderit. Et exercitation consequat ea Lorem. Id amet anim eiusmod ipsum
			elit cupidatat aliquip exercitation incididunt ullamco nulla. Deserunt cillum aute magna culpa
			anim qui. Anim sint eiusmod sint cupidatat ea enim Lorem culpa sunt aliquip aute proident.
			Aliqua officia proident laboris anim ullamco cillum veniam nisi minim ipsum. Et aliquip ad
			elit excepteur adipisicing adipisicing dolore commodo quis magna enim ut laboris. Cillum Lorem
			do culpa adipisicing nisi anim excepteur Lorem labore ut occaecat. Aliquip non esse quis nisi
			pariatur sit est. Aliquip pariatur amet est id aliqua officia non ex.
		</p>
		<p class="fade-in paragraph">
			Occaecat laboris est adipisicing magna adipisicing ea et. Commodo laborum irure sint irure
			dolore enim tempor eu labore qui magna. Qui non velit nulla irure aute eiusmod labore esse
			dolore exercitation duis Lorem. Elit deserunt cupidatat culpa et qui nisi duis in dolore
			proident velit incididunt. Officia aliquip minim excepteur consequat. Nisi irure mollit non ad
			incididunt quis. Nostrud do ipsum occaecat nisi ullamco cillum ea Lorem culpa aliqua magna sit
			sit. Ex aliqua laboris aliquip laboris anim aliqua incididunt. Cupidatat elit aute officia
			anim fugiat irure quis eu mollit consectetur aliqua laborum. Quis id voluptate irure
			incididunt consectetur aliquip et veniam reprehenderit eiusmod fugiat fugiat laborum. In nisi
			ipsum dolor commodo ut. Magna eu irure esse pariatur id laborum exercitation elit irure non.
			Laboris pariatur consectetur ex sunt ipsum amet. Fugiat pariatur officia nulla est cupidatat
			sint id officia ipsum. Aliquip duis incididunt dolor laborum voluptate incididunt culpa
			ullamco aute culpa irure amet. Elit laboris aliquip eiusmod officia et aliquip id nostrud. Est
			ut eiusmod do laborum et laborum labore incididunt dolor Lorem cupidatat esse Lorem.
		</p>
	</div>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Spline+Sans+Mono:wght@500&display=swap');

	#root-div {
		background-color: rgb(175, 40, 40);
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
	}

	.fade-in {
		opacity: 0;
	}

	.paragraph {
		padding: 10px 0;
		margin-left: 0.5rem;
	}
</style>
