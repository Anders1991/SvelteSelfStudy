<script>
import Menu from "./menu/Header.svelte";
import Introduction from "./introduction/Introduction.svelte";
import Reactivity from "./reactivity/Reactivity.svelte";
import Props from "./props/Props.svelte";
import Logic from "./logic/Logic.svelte";
import Events from "./events/Events.svelte";
</script>

<Menu />
<main>
	<div class="Page" id="Introduction">
		<Introduction />
	</div>

	<div class="Page" id="Reactivity">
		<Reactivity />
	</div>

	<div class="Page" id="Props">
		<Props />
	</div>

	<div class="Page" id="Logic">
		<Logic />
	</div>

	<div class="Page" id="Events">
		<Events />
	</div>

</main>

<style>

	.Page {
		display: none;
	}

	#Introduction {
		display: none;
	}

</style>