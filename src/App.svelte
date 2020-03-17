<script>
	import { onMount } from 'svelte';
	import SimpleMDE from "SimpleMDE";
	let editorElement;

	onMount(() => {
		const simplemde = new SimpleMDE({ element: editorElement });
	});
</script>

<main>
	<h1>Hello there!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<textarea bind:this={editorElement}></textarea>
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