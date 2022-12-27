<script>
    import items from "$lib/data/grid_data";

    /**
	 * @param {number} index
	 * @param {string} name
	 */
    function activate( index, name ) {
        items[index].active = !items[index].active;
        items.forEach(item => {
            if (item.index != index) 
                items[item.index].active = false;
        });

        console.log( name + ( items[index].active ? " activated." : " deactivated." ) );
    }

</script>

<div class="grid grid-cols-3 w-full">
    {#each items as item}
         <button class={'transition-all w-32 text-center my-auto px-1 py-2 border border-pink-500 rounded mx-1 ' 
         + (item.active ? 'bg-pink-500 text-white font-bold' : ``)} 
         on:click={_ => activate(item.index, item.name)}>{item.name}</button>
    {/each}
</div>