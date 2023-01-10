<script>
    export let text;

    import { createEventDispatcher } from 'svelte';
    import { onMount } from 'svelte';

    const dispatch = createEventDispatcher();

    function handleClick() {
        dispatch('update-header', {
            newHeader: text
        });
    }

    onMount(function() {
        let color = "#" + Math.floor(Math.random()*16777215).toString(16)
        document.getElementById(`menu-item-${text}`).style.color = color;
    });
</script>

<li>
    <!-- <a id="menu-item-{text}" href="/" on:click={handleClick}>{text}</a> -->
    <a id="menu-item-{text}" href="/" on:click|preventDefault={handleClick}>{text}</a>
</li>