<script>
    export let height, datum
    const { description, title } = datum
</script>

<li class="link-card" style="height: {height}px;">
    <a href="/{height}">
		<h2>
			{ title }
		</h2>
		<p>
			{ description }
		</p>
	</a>
</li>
<style>
    :global(body){

		--accent: 136, 58, 234;
		--accent-light: 224, 204, 250;
		--accent-dark: 49, 10, 101;
		--accent-gradient: linear-gradient(
			45deg,
			rgb(var(--accent)),
			rgb(var(--accent-light)) 30%,
			white 60%
		);
    }
	.link-card {
  position: absolute;
  width: 100px;
		list-style: none;
		padding: 1px;
		background-color: #23262d;
		background-image: none;
		background-size: 400%;
		border-radius: 7px;
		background-position: 100%;
		transition: background-position 0.6s cubic-bezier(0.22, 1, 0.36, 1);
		box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1);
	}
    h2, p {

        width: 70%;
        margin: auto;
    }
	.link-card > a {
		text-decoration: none;
		line-height: 1.4;
		padding: calc(1.5rem - 1px);
		border-radius: 8px;
		color: var(--fg-color-1);
		background-color: var(--bg-color-1);
		opacity: 0.8;
	}
	h2 {
		font-size: 1.25rem;
		transition: color 0.6s cubic-bezier(0.22, 1, 0.36, 1);
	}
	p {
		margin-block: 0.5rem;
	}
	.link-card:is(:hover, :focus-within) {
		background-position: 0;
         background-image: linear-gradient(rgba(var(--accent-dark), 66%), rgba(var(--accent-dark), 33%));
		/* background-image: var(--accent-gradient); */
	}
	.link-card:is(:hover, :focus-within) h2 {
		color: rgb(var(--accent-light));
	}
</style>
