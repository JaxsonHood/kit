<script>
	import KitBar from "$lib/components/KitBar.svelte";
    import "../app.css";
</script>
  
<div class="w-screen min-h-screen h-full bg-slate-900 p-3">
    <KitBar />
    <slot />
</div>