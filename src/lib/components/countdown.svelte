<script lang="ts">
	import Counter from '$lib/components/counter.svelte';
</script>

<div class="countdown">
	<div class="counter-container">
		<Counter count={8}></Counter>
		<p class="name">Days</p>
	</div>
	<div class="counter-container">
		<Counter count={23}></Counter>
		<p class="name">Hours</p>
	</div>
	<div class="counter-container">
		<Counter count={55}></Counter>
		<p class="name">Minutes</p>
	</div>
	<div class="counter-container">
		<Counter count={41}></Counter>
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
