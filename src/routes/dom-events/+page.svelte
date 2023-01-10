<script>
	let m = { x: 0, y: 0 };
    let objectPrinted = false;
    let objectPrinted2 = false;

	function handleMousemove(event) {
        if (!objectPrinted) {
            console.log(event);
        }
        
		m.x = event.clientX;
		m.y = event.clientY;
        objectPrinted = true;
	}

    function resetDisplay(event) {
        if (!objectPrinted2) {
            console.log(event);
        }

        m.x = 0;
        m.y = 0;

        objectPrinted2 = true;
    }
</script>

<br><br><br><br><br><br><br><br><br>

<div on:mousemove={handleMousemove} on:mouseleave={resetDisplay}>
	The mouse position is {m.x} x {m.y}
</div>

<style>
	div { 
        width: 90%; 
        height: 100%;
        padding: 20px;
        display: block;
        border-color: black;
        border-width: 3px;
        border-style: solid;
    }
</style>