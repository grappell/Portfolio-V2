<script>
	import Navbar from '../components/Navbar.svelte';
	import './../css/app.css';
</script>

<Navbar />
<div class="w-screen min-h-screen">
	<slot />
</div>
