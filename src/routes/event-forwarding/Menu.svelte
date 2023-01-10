<script>
	import MenuItem from "./MenuItem.svelte";
</script>
<ul>
    <MenuItem on:update-header text="Home"/>
    <MenuItem on:update-header text="About"/>
    <MenuItem on:update-header text="Contact Us"/>
</ul>
