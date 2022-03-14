<script>
    let count = 0;
    let count1 = 0;
    let count2 = 0;

    function handleClick() {
        count += 1;
    }

    function handleClick1() {
        count1 += 1;
    }

    // the `$:` means 're-run whenever these values change'
    $: doubled = count1 * 2;
	$: quadrupled = doubled * 2;

    $: if (count2 >= 10) {
		alert(`Watch out!`);
		count2 = 9;
	}

	function handleClick2() {
		count2 += 1;
	}

</script>

<main>
<h1>Reactivity</h1>

<div class="shadowBox">
    <p>1. Reactive Assignments</p>
    <p>This button uses a Javascript function to count the number of clicks</p>
    <button on:click={handleClick}>
        Clicked {count} {count === 1 ? 'time' : 'times'}
    </button>

</div>

<div class="shadowBox">
    <p>2. Reactive Declarations </p>
    <p>This Button counts the number of times it's clicked. But it also reactively changes the values below it.</p>
    <button on:click={handleClick1}>
    Count: {count1}
    </button>

    <p>{count1} * 2 = {doubled}</p>
    <p>{doubled} * 2 = {quadrupled}</p>
</div>

<div class="shadowBox">
    <p>3. Reactive statements</p>
    <p>This time, the button will throw an alert when clicked more than 9 times.</p>
    <button on:click={handleClick2}>
        Clicked {count2} {count2 === 1 ? 'time' : 'times'}
    </button>
</div>

</main>
