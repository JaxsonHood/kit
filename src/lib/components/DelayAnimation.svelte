<script>
    let loading = true;
    export let timeInMs;

    setTimeout(() => {
        loading = false;
    }, timeInMs);
</script>

{#if !loading}
    <slot/>
{/if}