<script>
import Nested from "./Nested.svelte";

let name = "World";
let src = 'SvelteLogo.png';
let pictureName = 'SvelteLogo';
let FiveString = 'This <b>string</b> has some html elements on <strong>it</strong>.';

</script>

<main>

	<h1>Introduction</h1>
	<p>This application demonstrate following the <a href="https://svelte.dev/tutorial">Svelte tutorial</a>.</p>
	
	<div class="shadowBox">
	<p>1. Hello World</p>
	<p>This exercise demonstrates the use of {'{name}'}. Hello {name}!</p>
	</div>

	<div class="shadowBox">
	<p>2. Dynamic attributes</p>
	<p>This exercise demonstrates the use of dynamic attributes such as the picture below.</p>
	<img {src} alt="{pictureName}">
	</div>

	<div class="shadowBox">
		<p>3. Styling</p>
		<p id="styling">This one is about styling.</p>
	</div>

	<div class="shadowBox">
		<p>4. Nested Components</p>
		<p>This is a styled paragraf</p>
		<Nested/>
	</div>

	<div class="shadowBox">
		<p>5. HTML tags</p>
		<p>{@html FiveString}</p>
	</div>

</main>


<style>

	#styling {
		font-size: 28px;
		color: red;
		font-family: 'Lobster';
		background-color: white;
		padding: 10px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>