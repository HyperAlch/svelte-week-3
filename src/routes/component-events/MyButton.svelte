<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function sayHello() {
        let randomNumber = Math.random()
		dispatch('button-clicked', {
			myMessage: 'Hello!',
            myNumber: randomNumber,
		});
	}
</script>

<button on:click={sayHello}>
	Click to say hello
</button>