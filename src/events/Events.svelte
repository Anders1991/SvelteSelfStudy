<script>
import Outer from './Outer.svelte';

// 1
let m = { x: 0, y: 0 };

function handleMousemove(event) {
    m.x = event.clientX;
    m.y = event.clientY;
}

// 2
let n = { x: 0, y: 0 };

// 3
function handleClick() {
		alert('Last chance!')
	}

// 4
import Inner from './Inner.svelte';

function handleMessage(event) {
    alert(event.detail.text);

}

</script>

<main>
    <h1>Events</h1>

    <div class="shadowBox">
        <p>1. Dom Events</p>
        <p>This box tracks where the mouse is in it.. pretty cool!</p>
        <div class="mousebox" on:mousemove={handleMousemove}>
            The mouse position is {m.x} x {m.y}
        </div>
    </div>

    <div class="shadowBox">
        <p>2. Inline Handlers</p>
        <p>The difference here from the previous example is that the event is handled inline instead of in the DOM.</p>
        <div class="mousebox" on:mousemove="{e => n = { x: e.clientX, y: e.clientY }}">
            The mouse position is {n.x} x {n.y}
        </div>
    </div>

    <div class="shadowBox">
        <p>3. Event Modifiers</p>
        <p>This button only gives you one warning!</p>
        <button on:click|once={handleClick}>
            Don't Click Me! 
        </button>
    </div>

    <div class="shadowBox">
        <p>4. Component Events</p>
        <p>This button is described in the component Inner.svelte. It throws an alert that says Hello.</p>
        <Inner on:message={handleMessage}/>
    </div>

    <div class="shadowBox">
        <p>5. Event Forwarding</p>
        <p>Here we forward the event from the Inner.svelte to the Outer.svelte </p>
        <Outer on:message={handleMessage}/>
    </div>

</main>

<style>
    .mousebox {
        display: flex;
        justify-content: center;
        background-color: white;
        height: 500px;
        width: 500px;
    }

</style>