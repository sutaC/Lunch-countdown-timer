<div class="links">
	<a
		id="facebook"
		href="https://www.facebook.com/"
		target="_blank"
		rel="noopener noreferrer"
		aria-label="Facebook"
	></a>
	<a
		id="pinterest"
		href="https://pinterest.com/"
		target="_blank"
		rel="noopener noreferrer"
		aria-label="Pinterest"
	></a>
	<a
		id="instagram"
		href="https://www.instagram.com/"
		target="_blank"
		rel="noopener noreferrer"
		aria-label="Instagram"
	></a>
</div>

<style>
	.links {
		width: 100%;
		height: 30vh;

		background: url('/images/pattern-hills.svg');
		background-repeat: no-repeat;
		background-size: cover;
		background-position: right bottom;

		display: flex;
		justify-content: center;
		align-items: center;
		gap: 2rem;
	}

	a {
		width: 1.75rem;
		aspect-ratio: 1;

		mask-position: center;
		mask-size: contain;
		mask-repeat: no-repeat;

		background: var(--clr-primary);

		transition: background-color 0.5s;
	}

	a:hover,
	a:focus {
		background: var(--clr-highlight);
		outline: none;
	}

	#facebook {
		mask-image: url('/images/icon-facebook.svg');
	}
	#pinterest {
		mask-image: url('/images/icon-pinterest.svg');
	}
	#instagram {
		mask-image: url('/images/icon-instagram.svg');
	}
</style>
