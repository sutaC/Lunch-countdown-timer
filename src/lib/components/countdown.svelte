<script lang="ts">
	import Counter from '$lib/components/counter.svelte';
</script>

<div class="countdown">
	<div class="counter-container">
		<Counter>8</Counter>
		<p class="name">Days</p>
	</div>
	<div class="counter-container">
		<Counter>23</Counter>
		<p class="name">Hours</p>
	</div>
	<div class="counter-container">
		<Counter>55</Counter>
		<p class="name">Minutes</p>
	</div>
	<div class="counter-container">
		<Counter>41</Counter>
		<p class="name">Seconds</p>
	</div>
</div>
