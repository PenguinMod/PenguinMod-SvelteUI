<script>
    import { page } from "$app/state";

    let { children } = $props();
    
    let theme = $derived(page.url.searchParams.get("theme"));
    const switchTheme = (theme) => {
        const searchParams = page.url.searchParams;
        searchParams.set("theme", theme);
        location.href = String(page.url);
    };
</script>

<main class={`theme-${theme}`}>
    <button onclick={() => switchTheme("light")}>Light</button>
    <button onclick={() => switchTheme("dark")}>Dark</button>
    <br>
    <a href={page.url.origin}>Home</a>
    <hr>
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