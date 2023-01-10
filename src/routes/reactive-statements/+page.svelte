<script>
    import { onMount } from 'svelte';
	let count = 0;
    let box = null;

    function handleClick() {
		count += 1;
	}

    // Runs every time count changes
    $: console.log('the count is ' + count);

    // Runs only after the if statement is met AND count changes
	$: if (count >= 10) {
		alert(`count is dangerously high!`);
		count = 9;
	}

    $: {
        if (box) {
            box.style.width = `${ (count + 1) * 50 }px`;
            box.style.height = `${ (count + 1) * 50 }px`;
        }
    }
   
    // Svelte code runs BEFORE html renders, so we have to wait until render to grab the box <div>
    onMount(function() {
        box = document.getElementById("box");
    });
 
   	
</script>

<button on:click={handleClick}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<br><br>

<div id="box"></div>

<style>
    #box {
        display: block;
        border-color: black;
        border-width: 3px;
        border-style: solid;
    }
</style>