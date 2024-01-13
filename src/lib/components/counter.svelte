<script lang="ts">
	export let count: number = 0;

	$: display = ((count) => {
		if (count < 10) {
			return '0' + count;
		}
		return count;
	})(count);
</script>

{#key display}
	<div class="counter">
		<div class="content" data-text-overlay={display}>
			{display}
		</div>
	</div>
{/key}

<style>
	.counter {
		--_clr-counter-up: color-mix(in srgb, var(--clr-counter) 100%, black 20%);

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

		background: var(--_clr-counter-up);
		border-radius: 0.3rem;
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
		box-shadow: 0 0 0.1rem 0.1rem hsla(0, 0%, 0%, 0.2);
	}

	.counter::before {
		background-color: var(--_clr-counter-up);
		top: 0;

		z-index: 1;
	}

	.counter::after {
		background-color: var(--clr-counter);
		bottom: 0;
	}

	.content {
		position: relative;
		z-index: 10;
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

	/* animations */

	@keyframes flip {
		0% {
			transform: rotateX(0deg);
		}
		100% {
			transform: rotateX(180deg);
		}
	}

	@keyframes slide {
		0% {
			translate: 0 0;
			background-color: var(--_clr-counter-up);
		}

		100% {
			translate: 0 100%;
			background-color: var(--clr-counter);
		}
	}

	@keyframes darkening {
		0% {
			background-color: var(--clr-counter);
			opacity: 1;
		}
		100% {
			background-color: black;
			opacity: 0.2;
		}
	}

	/* --- */

	.counter {
		--_animation-duration: 0.4s;
	}

	.counter::before {
		animation:
			flip var(--_animation-duration) ease-out,
			slide var(--_animation-duration) ease-out;
	}

	.counter::after {
		animation: darkening var(--_animation-duration) ease-in;
	}
</style>
