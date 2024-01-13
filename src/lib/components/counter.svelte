<script lang="ts">
	export let count: number = 0;
	$: display = ((count) => {
		if (count < 10) {
			return '0' + count;
		}
		return count;
	})(count);
</script>

<div class="counter">
	<div class="content" data-text-overlay={display}>
		{display}
	</div>
</div>

<style>
	.counter {
		width: 100%;
		height: 100%;
		aspect-ratio: 1;
		position: relative;
		isolation: isolate;

		padding: 0.2em;

		display: grid;
		place-content: center;

		font-size: clamp(2.5rem, 8vw, 4rem);
		color: var(--clr-highlight);

		box-shadow: 0 3px 1px hsl(0, 0%, 0%, 0.2);
	}

	.counter::before,
	.counter::after {
		content: '';
		width: 100%;
		height: 50%;
		aspect-ratio: 1 / 2;

		display: block;
		position: absolute;
		left: 0;

		border-radius: 0.3rem;
		box-shadow: 0 0 4px hsla(0, 0%, 0%, 0.2);
	}

	.counter::before {
		--_clr-counter-up: color-mix(in srgb, var(--clr-counter) 100%, black 20%);
		background-color: var(--_clr-counter-up);
		top: 0;
	}

	.counter::after {
		background-color: var(--clr-counter);
		bottom: 0;
	}

	.content {
		position: relative;
		z-index: 1;
		overflow: hidden;
	}

	.content::before {
		content: attr(data-text-overlay);
		width: 100%;
		height: 50%;
		display: block;
		position: absolute;
		opacity: 0.2;
		overflow: hidden;
		color: black;
	}
</style>
