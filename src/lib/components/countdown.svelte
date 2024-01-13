<script lang="ts">
	import Counter from '$lib/components/counter.svelte';

	let days: number = 14;
	let hours: number = 0;
	let minutes: number = 0;
	let seconds: number = 0;

	const counter = setInterval(() => {
		seconds--;
		updateCounter();
	}, 1000);

	function updateCounter() {
		if (seconds < 0) {
			seconds = 59;
			minutes--;
		}
		if (minutes < 0) {
			minutes = 59;
			hours--;
		}
		if (hours < 0) {
			hours = 23;
			days--;
		}
		if (days < 0) {
			clearInterval(counter);
			days = hours = minutes = seconds = 0;
		}
	}
</script>

<div class="countdown">
	<div class="counter-container">
		<Counter count={days}></Counter>
		<p class="name">Days</p>
	</div>
	<div class="counter-container">
		<Counter count={hours % 24}></Counter>
		<p class="name">Hours</p>
	</div>
	<div class="counter-container">
		<Counter count={minutes % (24 * 60)}></Counter>
		<p class="name">Minutes</p>
	</div>
	<div class="counter-container">
		<Counter count={seconds % (24 * 60 * 60)}></Counter>
		<p class="name">Seconds</p>
	</div>
</div>

<style>
	.countdown {
		display: flex;
		justify-content: space-evenly;
		align-items: center;
		gap: 1rem;

		padding: 1rem;
		width: clamp(40%, 27.5rem, 100%);
		margin: 0 auto;
	}

	.counter-container {
		flex: 1;
	}

	.name {
		max-width: 100%;

		color: var(--clr-primary);
		text-transform: uppercase;
		font-size: 0.6rem;
		letter-spacing: 0.2em;
	}
</style>
