<script>
import NestedProps from "./NestedProps.svelte";
import Info from "./Info.svelte";

const Anders = {
    name: 'Anders',
    age: '30',
    gender: 'Male'
};

</script>

<main>
    <h1>Props</h1>

    <div class="shadowBox">
        <p>1. Declaring Props</p>
        <p>Props can come from other .svelte files. For instance the following:</p>
        <NestedProps answer={"Yes!"} />

    </div>

    <div class="shadowBox">
        <p>2. Default Values</p>
        <p>You can assign default values to your props. Here yes is the default value.</p>
        <NestedProps answer={"No"}/>
        <NestedProps/>
    </div>

    <div class="shadowBox">
        <p>3. Spread Props</p>
        <p>You can use multiple props however you see fit. The following sentence is made with props</p>
        <Info {...Anders} />
    </div>

</main>