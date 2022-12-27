<script>
	import Banner from "$lib/components/Banner.svelte";

    import Fa from 'svelte-fa'
    import { faPlus } from '@fortawesome/free-solid-svg-icons'

    import { fly, slide, scale } from "svelte/transition";
    import { quintOut } from "svelte/easing";
	import DelayAnimation from "$lib/components/DelayAnimation.svelte";
	import GridExample from "$lib/components/GridExample.svelte";

    const customTransition = { delay: 0, duration: 150, easing: quintOut }
</script>

<svelte:head>
    <title>KIT Coming Soon</title>
    <meta name="description" content="KIT a interactive way of managing flows.">
</svelte:head>

<DelayAnimation timeInMs=10>
    <div class="flex flex-col justify-center items-center text-slate-400 mt-24" in:scale={customTransition}>
        <div class="flex flex-row space-x-6 items-center">
            <h1 class="text-4xl font-semibold underline">
                Hello from:
            </h1>
            <div class="px-2 py-1 rounded-xl bg-lime-400 text-slate-900 cursor-pointer shadow-lg shadow-lime-400/30 hover:scale-110 transition-all">
                <h1 class="text-5xl font-mono font-extrabold">KIT</h1>
            </div>
        </div>
        <div class="flex flex-row justify-center mt-6">
            <a class="px-3 py-2 font-bold rounded-3xl border-2 border-slate-400 shadow shadow-slate-400/30 hover:border-slate-50 hover:text-slate-200 hover:shadow-lg hover:shadow-slate-400/30 transition-all flex flex-row space-x-2 items-center" 
               href="/create">
                <h3>CREATE</h3>
                <Fa class="hover:scale-110 transition-all" icon={faPlus} />
            </a>
        </div>
        <div class="mt-16">
            <Banner />
        </div>
        <div class="mt-16">
            <GridExample />
        </div>
    </div>
</DelayAnimation>
