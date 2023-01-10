<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    function submitForm(event) {
        let username = event.target[0].value;
        dispatch('form-submitted', {
            username: username,
        });
    }
</script>

<form on:submit={submitForm}>
    <input type="text" id="username" placeholder="Username">
    <input type="submit">
</form>