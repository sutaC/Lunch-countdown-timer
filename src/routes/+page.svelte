<script lang="ts">
	import Footer from '$lib/components/footer.svelte';
	import Links from '$lib/components/links.svelte';
	import Countdown from '$lib/components/countdown.svelte';
</script>

<svelte:head>
	<title>Frontend Mentor | Launch countdown timer</title>
</svelte:head>

<div class="app">
	<h1>We're launching soon</h1>

	<Countdown></Countdown>

	<Links></Links>
	<Footer></Footer>
</div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
	}

	.app {
		width: 100vw;
		min-height: 100vh;
	}

	h1 {
		margin: 0;
	}
</style>
