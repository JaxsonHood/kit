<script>
    import Fa from 'svelte-fa'
    import { faChevronCircleLeft, faChevronCircleRight } from '@fortawesome/free-solid-svg-icons'

    import { fly, slide, scale } from "svelte/transition";
    import { quintOut } from "svelte/easing";

    const customTransition = { delay: 0, duration: 150, easing: quintOut }

    let open = false;

    function toggleOpen() {
        open = !open;
    }
</script>

<div class="h-20">
    {#if open}
    <div class={`border-2 rounded-lg border-sky-200 mb-10 items-center transition-all ` + (open ? `w-full` : `w-min`)} in:slide={customTransition}>
        <div class="flex flex-row m-2 space-x-2">
            <div class="px-1 py-0.5 rounded-md rounded-bl rounded-tr bg-sky-300 text-slate-900 cursor-pointer w-min">
                <h1 class="text-3xl font-mono font-semibold whitespace-nowrap"><span class="font-extrabold">KIT</span>-Bar</h1>
            </div>

            <button aria-label="close-button" class="px-1 py-0.5 text-sky-300 text-3xl cursor-pointer w-min flex flex-row justify-center items-center border-2 border-sky-400 p-1 rounded-lg hover:shadow-lg hover:shadow-sky-300/20 hover:border-sky-400" on:click={toggleOpen} in:scale={customTransition}>
                <Fa class="hover:scale-95 transition-all" icon={faChevronCircleLeft} />
            </button>
        </div>
    </div>
    {:else}
    <div class={`border-2 rounded-lg border-sky-200 mb-10 items-center transition-all ` + (open ? `w-full` : `w-min`)} in:fly={{x:25, duration:200}}>
        <div class="flex flex-row m-2 space-x-2">
            <div class="px-1 py-0.5 rounded-md rounded-bl rounded-tr bg-sky-300 text-slate-900 cursor-pointer w-min">
                <h1 class="text-3xl font-mono font-semibold whitespace-nowrap">KIT-Bar</h1>
            </div>
            
            <button aria-label="open-button" class="px-1 py-0.5 text-sky-200 text-3xl cursor-pointer w-min flex flex-row justify-center items-center border-2 border-sky-300 p-1 rounded-lg hover:shadow-lg hover:shadow-sky-300/20 hover:border-sky-400" on:click={toggleOpen} in:scale={customTransition}>
                <Fa class="hover:scale-95 transition-all" icon={faChevronCircleRight} />
            </button>
        </div>
    </div>
    {/if}
</div>