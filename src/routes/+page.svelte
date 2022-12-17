<script>
	import Banner from "$lib/components/Banner.svelte";

</script>
<svelte:head>
    <title>KIT Coming Soon</title>
</svelte:head>

<div class="flex flex-col justify-center items-center text-slate-400 mt-36">
    <div class="flex flex-row space-x-6 items-center">
        <h1 class="text-4xl font-semibold underline">
            Hello from:
        </h1>
        <div class="px-2 py-1 rounded-xl bg-lime-500 text-slate-900 cursor-pointer shadow-lg shadow-lime-400/30 hover:scale-110 transition-all">
            <h1 class="text-5xl font-mono font-extrabold">KIT</h1>
        </div>
    </div>
    <div class="flex flex-row justify-center mt-6">
        <a class="px-3 py-2 font-bold rounded-3xl border-2 border-slate-400 shadow shadow-slate-400/30 hover:border-slate-50 hover:text-slate-200 hover:shadow-lg hover:shadow-slate-400/30 transition-all" 
           href="/create">
            CREATE
        </a>
    </div>
    <div class="mt-16">
        <Banner />
    </div>
</div>
