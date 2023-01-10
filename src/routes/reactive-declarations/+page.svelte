<script>
	let count = 1;
    let randomNumber = Math.random();
    

	// the `$:` means 're-run whenever these values change'
	$: doubled = count * 2;
	$: quadrupled = doubled * 2;

    $: randomNumberDisplay = "Random Number: " + randomNumber;
    $: randomNumberDisplayBold = `<b>${randomNumberDisplay}</b>`;

	function handleClick() {
		count += 1;
        randomNumber = Math.random();
	}

</script>

<button on:click={handleClick}>
	Count: {count}
</button>

<p>{count} * 2 = {doubled}</p>
<p>{doubled} * 2 = {quadrupled}</p>

<br><br>
<p>{randomNumberDisplay}</p>
<p>{@html randomNumberDisplayBold}</p>