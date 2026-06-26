<script>
    /**
     * @typedef {Object} Properties
     * @property {"dark"|null} theme Forces a specific theme
     */
    /** @type {Properties} */
    const props = $props();
    let theme = $derived(props.theme);
</script>

<div
    {...props}
    data-penguinmodsvelteui-category="true"
    class={`category${theme ? ` theme-${theme}` : ""}`}
>
    {#if props.header || props.headerSecondary}
        <div class="category-header">
            {#if props.header}
                <p
                    class="category-header-left"
                    data-penguinmodsvelteui-category-headerleft="true"
                >
                    {@render props.header()}
                </p>
            {/if}
            {#if props.headerSecondary}
                <p
                    class="category-header-secondary"
                    data-penguinmodsvelteui-category-headersecondary="true"
                >
                    {@render props.headerSecondary()}
                </p>
            {/if}
        </div>
    {/if}
    <div style={props.styleContainer || ""} class="category-container">
        {@render props.children?.()}
    </div>
</div>

<style>
    .category {
        width: 30%;
        margin: 10px;
        padding: 4px;

        border-radius: 8px;
        border-width: 1px;
        border-color: rgba(0, 0, 0, 0.3);
        border-style: solid;
    }
    .category-header {
        margin: 0 0.35rem;
        border-bottom: 1px solid rgba(0, 0, 0, 0.15);

        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .category-header-left {
        margin-block: 6px;
        font-weight: bold;
    }
    .category-header-secondary {
        margin-block: 6px;
    }
    .category-header-secondary :global(a) {
        color: dodgerblue;
    }
    .category-container {
        height: 312px;
        margin: 6px;

        overflow: auto;
    }

    .theme-dark.category,
    :global(body.penguinmodsvelteui-theme-dark) {
        border-color: rgba(255, 255, 255, 0.3);
    }
    .theme-dark .category-header,
    :global(body.penguinmodsvelteui-theme-dark) {
        border-bottom: 1px solid rgba(255, 255, 255, 0.15);
    }
</style>
