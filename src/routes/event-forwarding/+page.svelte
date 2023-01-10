<script>
	import LayerOne from './LayerOne.svelte';
	import Menu from './Menu.svelte';
	let menuHeader = "Home";

	function handleMessage(event) {
		alert(event.detail.text);
	}

    function handleUpdateHeader(event) {
        menuHeader = event.detail.newHeader;
    }
    
</script>

<h1>{menuHeader}</h1>

<LayerOne on:message={handleMessage}/>
<Menu on:update-header={handleUpdateHeader} />