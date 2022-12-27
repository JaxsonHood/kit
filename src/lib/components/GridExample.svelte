<script>
    import items from "$lib/data/grid_data";

    /**
	 * @type {any[]}
	 */
    let records = [];

    /**
	 * @type {HTMLDivElement}
	 */
    let scrollBoxObj;

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
    };

    const AddRecord = ( /** @type {any} */ item ) => {
        // Avoid using the push method so that only new records re-render
        records[records.length] = {item: item, time: Date.now(), action: item.active ? "activated" : "deactivated"};
        scrollToBottom();
    }

    const scrollToBottom = () => {
        if ( scrollBoxObj && scrollBoxObj.scrollTop < scrollBoxObj.scrollHeight )
            scrollBoxObj.scrollTop = scrollBoxObj.scrollHeight;
    }
</script>

<div>
    <div class="grid grid-cols-3 w-full">
        {#each items as item}
             <button class={'transition-all w-[105px] text-center my-auto px-1 py-2 border border-pink-500 rounded mx-1 ' 
             + (item.active ? 'bg-pink-500 text-white font-bold' : ``)} 
             on:click={() => Activate(item.index, item.name)}>{item.name}</button>
        {/each}
    </div>

    <div class="mt-10 overflow-y-auto max-h-96" bind:this={scrollBoxObj}>
        {#each records as record, i}
            {#key i}
            <h4 class="text-slate-400">{record.item.name} - action:{record.action}, time:{record.time}</h4>
            {/key}
        {/each}
    </div>
</div>