<script lang="ts">
	import Footer from '$lib/components/footer.svelte';
	import Links from '$lib/components/links.svelte';
	import Countdown from '$lib/components/countdown.svelte';
</script>

<svelte:head>
	<title>Frontend Mentor | Launch countdown timer</title>
	<meta name="description" content="A page counting down the time until the product is available" />
</svelte:head>

<div class="page">
	<main>
		<h1>We're launching soon</h1>

		<Countdown></Countdown>
	</main>

	<Links></Links>
	<Footer></Footer>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Red+Hat+Text:wght@700&display=swap');

	:root {
		--clr-primary: hsl(237, 18%, 59%);
		--clr-highlight: hsl(345, 95%, 68%);

		--clr-text: hsl(0, 0%, 100%);
		--clr-counter: hsl(236, 21%, 26%);
		--clr-shadow: hsl(235, 16%, 14%);
		--clr-bg-main: hsl(234, 17%, 12%);
	}

	:global(*) {
		box-sizing: border-box;
	}

	:global(html) {
		font-family: 'Red Hat Text', sans-serif;
		color: var(--clr-text);
	}

	:global(body) {
		margin: 0;
		padding: 0;
	}

	/* Main */

	.page {
		width: 100vw;
		min-height: 100vh;

		text-align: center;
		background:
			url('/images/bg-stars.svg') center,
			var(--clr-bg-main);
	}

	main {
		display: flex;
		justify-content: center;
		flex-direction: column;
		gap: 3rem;

		height: 70vh;
	}

	h1 {
		margin: 0;
		font-size: 1.2rem;
		text-transform: uppercase;
		letter-spacing: 0.4em;
	}
</style>
