<script>
	let mousePosition = { x: 0, y: 0 };

    function handleMousemove(event) {
        mousePosition = { x: event.clientX, y: event.clientY };
    }
</script>

<div on:mousemove="{handleMousemove}">
	The mouse position is {mousePosition.x} x {mousePosition.y}
</div>
<br><br>
<div on:mousemove="{event => mousePosition = { x: event.clientX, y: event.clientY }}">
	The mouse position is {mousePosition.x} x {mousePosition.y}
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