<script>
	import CustomButton from './CustomButton.svelte';

	function handleClick(event) {
		alert('clicked');
        console.log(event)
	}
</script>

<CustomButton on:click={handleClick}/>