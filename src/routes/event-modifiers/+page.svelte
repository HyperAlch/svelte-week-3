<script>
	function handleClick() {
		alert('no more alerts')
	}

    function sayHi(event) {
        let firstName = event.target[0].value
        let lastName = event.target[1].value


        alert(`Hello, ${firstName} ${lastName}`)

        // Get the action url
        let actionURL = event.target.action

        // Send the data to the URL via a javascript call
        // This means no page reload!
        console.log(actionURL)
    }

</script>

<button on:click|once={handleClick}>
	Click me
</button>

<br><br>
<form on:submit={sayHi} action="/action-page" method="post">
    <p>Form</p>
    First name <input id="first_name" type="text" required>
    <br><br>
    Last name <input id="last_name" type="text" required>
    <br><br>
    <input type="submit">
</form>

<br><br>
<form on:submit|preventDefault={sayHi} action="/action-page" method="post">
    <p>Form</p>
    First name <input id="first_name2" type="text" required>
    <br><br>
    Last name <input id="last_name2" type="text" required>
    <br><br>
    <input type="submit">
</form>