<script>
	import { onMount } from 'svelte';
	import SimpleMDE from "SimpleMDE";
	let editorElement;
	let simplemde;

	onMount(() => {
		simplemde = new SimpleMDE({
			autosave: {
				enabled: true,
				uniqueId: "MyUniqueID",
				delay: 1000,
			},
			placeholder: "Press F9 to enter and exit side-by-side with live preview. Press F11 to enter and exit fullscreen mode.",
			hideIcons: ["preview"],
			element: editorElement
		});
	});

	function reset() {
		simplemde.value("");
	}
</script>

<main>
	<h1>Hello there!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<div class="editor">
		<div class="header">
			<h1>News Editor</h1>
		</div>

		<div class="ui grid">
			<div class="sixteen wide column">
				<textarea bind:this={editorElement}></textarea>
			</div>
		</div>

		<div class="footer">
			<button class="save">Save</button>
			<button class="cancel" on:click={reset}>Cancel</button>
		</div>
	</div>
</main>

<style>
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		width: 100%;
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

	.editor {
		width: 90%;
		margin-left: 5%;
		display: flex;
		flex-direction: column;
	}

	.header {
		background-color: rgb(92, 92, 252);
		padding: 20px;
	}

	.ui {
		flex-grow: 2;
	}

	.footer {
		background-color: rgb(92, 92, 252);
		display: flex;
		flex-direction: row-reverse;
		padding: 20px;
	}

	button {
		margin-right: 30px;
		border: none;
		padding: 10px;
	}

	.save {
		background-color: yellow;
	}

	.cancel {
		background-color: orange;
	}
</style>