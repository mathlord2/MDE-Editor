<script>
	import SimpleMDE from "SimpleMDE";
	window.onload = function() {
		const simplemde = new SimpleMDE({ element: document.getElementById("newsEditor") });
	}
</script>

<main>
	<h1>Hello there!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<textarea id="newsEditor"></textarea>
</main>

<style>
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	#newsEditor {
		margin-top: 10px;
	}
</style>