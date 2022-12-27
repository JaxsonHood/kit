<script>
    import items from "$lib/data/grid_data";

    /**
	 * @type {any[]}
	 */
    let records = [];

    /**
	 * @param {number} i
	 * @param {string} name
	 */
    const Activate = ( i, name ) => {
        items[i].active = !items[i].active;
        items.forEach(item => {
            if (item.index != i) 
                items[item.index].active = false;
        });

        AddRecord( items[i] );
        PrintState( items[i] );
    };

    const PrintState = ( /** @type {any} */ item ) => {
        console.log( item.name + ( item.active ? " activated." : " deactivated." ) );
    }

    const AddRecord = ( /** @type {any} */ item ) => {
        let newRecs = records;
        newRecs.push(
            {item: item, time: Date.now(), action: item.active ? "state_activate" : "state_deactivate"}
        );
        records = newRecs; // This sets the array list so sveltekit knows to rerender the records each block
    }
</script>

<div>
    <div class="grid grid-cols-3 w-full">
        {#each items as item}
             <button class={'transition-all w-32 text-center my-auto px-1 py-2 border border-pink-500 rounded mx-1 ' 
             + (item.active ? 'bg-pink-500 text-white font-bold' : ``)} 
             on:click={() => Activate(item.index, item.name)}>{item.name}</button>
        {/each}
    </div>

    <div class="mt-10 overflow-y-auto max-h-96">
        {#each records as record}
            <h4 class="text-slate-400">{record.item.name} - action:{record.action}, time:{record.time}</h4>
        {/each}
    </div>
</div>