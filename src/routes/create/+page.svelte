<script>
	import { fly, slide, scale } from "svelte/transition";
    import { quintOut } from "svelte/easing";
	import DelayAnimation from "$lib/components/DelayAnimation.svelte";

    const customTransition = { delay: 0, duration: 150, easing: quintOut }
</script>

<svelte:head>
    <title>Create New</title>
    <meta name="description" content="Create a new KIT Scheme.">
</svelte:head>

<DelayAnimation timeInMs=10>
    <div class="flex flex-col justify-center items-center mt-24" in:scale={customTransition}>
        <div class="flex flex-row space-x-6 items-center">
            <h1 class="text-4xl font-semibold font-mono text-slate-400 px-4 py-2 outline-double rounded-xl">
                CREATE NEW
            </h1>
        </div>
    </div>
</DelayAnimation>