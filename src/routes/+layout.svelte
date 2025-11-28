<script>
    import { page } from "$app/state";

    let { children } = $props();
    
    let theme = $derived(page.url.searchParams.get("theme"));
</script>

<main class={`theme-${theme}`}>
    {@render children?.()}
</main>

<style>
    main {
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;

        overflow: auto;
    }

    .theme-dark {
        background: #111;
    }
</style>