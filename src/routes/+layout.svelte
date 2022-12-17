<script>
	import KitBar from "$lib/components/KitBar.svelte";
    import "../app.css";
</script>
  
<div class="w-screen h-screen bg-slate-900 p-3">
    <KitBar />
    <slot />
</div>