<script>
	let count = 0;

	function handleClick() {
		count += 1;
	}
</script>

<button on:click={handleClick}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<!-- This way is a little to verbose, there is a better pattern! -->
{#if count > 5 && count <= 10}
    <p>Count is higher than 5</p>
{/if}

{#if count > 10 && count <= 12}
    <p>Count is higher than 10</p>
{/if}

{#if count > 12}
    <p>Count is higher than 12</p>
{/if}

<!-- Much shorter AND easier to read! -->
<p>
    {count > 5 && count <= 10 ? 'Count is higher than 5' : ''}
    {count > 10 && count <= 12 ? 'Count is higher than 10' : ''}
    {count > 12 ? 'Count is higher than 12' : ''}
</p>