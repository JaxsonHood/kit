<script>
	import Toolbar from "$lib/components/Toolbar.svelte";
    import "../app.css";
</script>
  
<div class="w-screen h-screen bg-slate-900 p-2">
    <Toolbar />
    <slot />
</div>