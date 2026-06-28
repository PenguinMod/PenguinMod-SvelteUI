<script>
    /**
     * @typedef {Object} Properties
     * @property {"dark"|null} theme Forces a specific theme
     */
    /** @type {Properties} */
    const props = $props();
    let theme = $derived(props.theme);

    let holderFirst = $derived(Object.keys(props).filter(key => key.startsWith("swap"))[0].slice(4));
    let holderSelected = $derived(holderFirst);
    const holderSelect = (holderName) => {
        holderSelected = holderName;
        if (props.onchange) props.onchange(holderName);
    };
</script>

<div
    class="sh"
    data-penguinmodsvelteui-swappableholder="true"
    {...props}
>
    <div
        class="sh-header"
        data-penguinmodsvelteui-swappableholder-header="true"
    >
        {#each Object.keys(props) as snippet}
            {#if snippet.startsWith("holder") && snippet.slice(6) === holderSelected}
                {@render props[snippet]()}
            {/if}
        {/each}
    </div>
    <div
        class="sh-footer"
        data-penguinmodsvelteui-swappableholder-footer="true"
    >
        {#each Object.keys(props) as snippet}
            {#if snippet.startsWith("swap")}
                <button
                    class="sh-footer-swapper"
                    data-checked={snippet.slice(4) === holderSelected}
                    data-penguinmodsvelteui-swappableholder-footer-swapper="true"
                    onclick={() => holderSelect(snippet.slice(4))}
                >
                    {@render props[snippet]()}
                </button>
            {/if}
        {/each}
    </div>
</div>

<style>
    .sh {
        width: 100%;

        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .sh-header,
    .sh-footer {
        margin: 4px 0;
    }

    .sh-footer-swapper {
        border: 0;
        margin: 8px 4px;
        padding: 4px 8px;

        background: #008cff;
        color: white;
        border-radius: 1024px;
        font-weight: bold;

        cursor: pointer;
        user-select: none;
    }
    .sh-footer-swapper[data-checked=true] {
        background: #003bdd;
    }
    .sh-footer-swapper:hover {
        filter: brightness(1.1);
    }
    .sh-footer-swapper:active {
        filter: brightness(0.9);
    }

    .sh-footer-swapper:empty {
        padding: 8px;
    }
</style>