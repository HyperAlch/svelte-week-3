<script>
	import MyButton from './MyButton.svelte';
    import MyForm from './MyForm.svelte';

    let username = null;

	function handleButtonClick(event) {
		alert(event.detail.myMessage);
        alert(event.detail.myNumber);
	}

    function handleFormSubmit(event) {
        username = event.detail.username
    }
</script>

{#if username}
    <h1>Welcome, {username}</h1>
{/if}

<MyButton on:button-clicked={handleButtonClick}/>

<br><br>

<MyForm on:form-submitted={handleFormSubmit}/>