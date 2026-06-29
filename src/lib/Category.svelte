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
                    class="category-header-text"
                    data-penguinmodsvelteui-category-headertext="true"
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
    <div
        style={props.styleContainer || ""}
        class="category-container"
        data-penguinmodsvelteui-category-container="true"
        data-penguinmodsvelteui-category-container-hasheader={!!props.header}
        data-penguinmodsvelteui-category-container-hasheadersecondary={!!props.headerSecondary}
        data-penguinmodsvelteui-category-container-hasfooter={!!props.footer}
    >
        {@render props.children?.()}
    </div>
    {#if props.footer}
        <div class="category-footer">
            <p>
                {@render props.footer()}
            </p>
        </div>
    {/if}
</div>

<style>
    .category {
        /* (margin + padding + border) * 2 */
        width: calc(100% - ((10px + 4px + 1px) * 2));
        height: 312px;
        margin: 10px;
        padding: 4px;

        display: flex;
        flex-direction: column;

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
    .category-header-text {
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
        flex: 1;
        margin: 6px;

        overflow: auto;
    }
    
    .category-footer {
        width: calc(100% - 0.35rem);
        margin: 0 0.35rem;
        border-top: 1px solid rgba(0, 0, 0, 0.15);
    }
    .category-footer p {
        width: 100%;
        margin-block: 0;
        margin-block-start: 8px;
        margin-block-end: 4px;

        text-overflow: ellipsis;
        white-space: nowrap;
        overflow: hidden;
    }

    .theme-dark.category,
    :global(body.penguinmodsvelteui-theme-dark) .category {
        border-color: rgba(255, 255, 255, 0.3);
    }
    .theme-dark .category-header,
    :global(body.penguinmodsvelteui-theme-dark) .category-header {
        border-bottom: 1px solid rgba(255, 255, 255, 0.15);
    }
    .theme-dark .category-footer,
    :global(body.penguinmodsvelteui-theme-dark) .category-footer {
        border-top: 1px solid rgba(255, 255, 255, 0.15);
    }
</style>
