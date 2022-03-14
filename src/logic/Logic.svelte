<script>
	import Thing from './Thing.svelte';

// 1
   let user = { loggedIn: false };

function toggle() {
    user.loggedIn = !user.loggedIn;
} 

// 2 
let user1 = { loggedIn: false };

function toggle1() {
    user1.loggedIn = !user1.loggedIn;
} 

// 3
let x = 0;

function Clickity() {
        x += 1;
    }

// 4
let memes = [
    {id: 'dNQs_Bef_V8', name: 'Omae wa mou shindeiru'},
    {id: 'LD8P8Mq3rVU', name: 'Do you know da wae?'},
    {id: 'dQw4w9WgXcQ', name: 'Rick Roll'},
]

// 5
let things = [
		{ id: 1, color: 'darkblue' },
		{ id: 2, color: 'indigo' },
		{ id: 3, color: 'deeppink' },
		{ id: 4, color: 'salmon' },
		{ id: 5, color: 'gold' }
	];

	function handleClick() {
		things = things.slice(1);
	}
</script>



<main>

    <h1>Logic</h1>

    <div class="shadowBox">
        <p>1. If Blocks</p>
        <p>Here we create a button and which can toggle between being logged in and logged out.</p>
        {#if user.loggedIn}
    	    <button on:click={toggle}>
	    	    Log out
    	    </button>
        {/if}

        {#if !user.loggedIn}
	        <button on:click={toggle}>
	        	Log in
	        </button>
        {/if}
    </div>

    <div class="shadowBox">
        <p>1. Else Blocks</p>
        <p>here we create the same button, but with an if/else statement.</p>
        {#if user1.loggedIn}
	        <button on:click={toggle1}>
	        	Log out
	        </button>
        {:else}
	        <button on:click={toggle1}>
		        Log in
	        </button>
        {/if}
    </div>
    
    <div class="shadowBox">
        <p>1. Else-if Blocks</p>
        <p>This code evaluates the value x and outputs an appropriate message.</p>
        {#if x > 10}
	        <p>{x} is greater than 10</p>
        {:else if 5 > x}
	        <p>{x} is less than 5</p>
        {:else}
	        <p>{x} is between 5 and 10</p>
        {/if}
        <button on:click={Clickity}>
            Clicked {x} {x === 1 ? 'time' : 'times'}
        </button>
    </div>

    <div class="shadowBox">
        <p>1. Each Blocks</p>
        <p>Here is a list of some memes on youtube</p>
        <ul>
            {#each memes as { id, name }, i}
                <li>
                    <a target="_blank" href="https://www.youtube.com/watch?v={id}">
                        {i + 1}: {name}
                    </a>
                </li>
            {/each}
        </ul>
    </div>

    <div class="shadowBox">
        <p>1. Keyed each Blocks</p>
        <button on:click={handleClick}>
            Remove first thing
        </button>
        
        <div style="display: grid; grid-template-columns: 1fr 1fr; grid-gap: 1em">
            <div>
                <h2>Keyed</h2>
                {#each things as thing (thing.id)}
                    <Thing current={thing.color}/>
                {/each}
            </div>
        
            <div>
                <h2>Unkeyed</h2>
                {#each things as thing}
                    <Thing current={thing.color}/>
                {/each}
            </div>
        </div>
    </div>
</main>

<style>
    a {
        color: white;
    }

</style>