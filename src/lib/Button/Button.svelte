<script>
    /**
     * @typedef {Object} Properties
     * @property {string?} link A link to redirect to when the button is clicked
     * @property {boolean?} noredirect If link is defined, the link will open in a new tab
     * @property {"highlighted"|"border"|null} kind Whether the button is usable or not
     * @property {string?} icon An image URL to put next to the button
     * @property {"dark"|null} theme Forces a specific theme
     * @property {string?} color CSS color for the button
     */
    /** @type {Properties} */
    const props = $props();
    let link = $derived(props.link);
    let noredirect = $derived(props.noredirect);

    // style
    let kind = $derived(props.kind);
    let icon = $derived(props.icon);
    let theme = $derived(props.theme);
    let color = $derived(props.color); // TODO: Implement this
</script>

{#snippet button()}
    <button
        {...props}
        data-penguinmodsvelteui-button="true"
        class={`button${kind ? ` button-kind-${kind}` : ""}${` theme-${theme}`} ${props.class || ""}`}
    >
        <div>
            {#if icon}
                <img
                    src={icon}
                    alt={icon}
                    class="button-icon"
                />
            {/if}
            {@render props.children?.()}
        </div>
    </button>
{/snippet}
{#if link}
    <a
        href={link}
        target={noredirect ? "_blank" : "_self"}
        style="text-decoration: none;"
        data-penguinmodsvelteui-button-link="true"
    >
        {@render button()}
    </a>
{:else}
    {@render button()}
{/if}

<style>
    .button {
        margin: 0.25rem;
        padding: 1rem 1rem;
        
        font-weight: 600;
        font-size: 1.1rem;
        border: 0px;
        border-radius: 4px;
        outline-width: 2px;
        outline-style: solid;
        outline-color: rgba(0, 195, 255, 0.35);
        color: white;
        background-color: #00c3ff;

        cursor: pointer;
    }
    .button:focus {
        outline-width: 4px;
    }
    .button > div {
        display: flex;
        flex-direction: row;
        align-items: center;
    }
    .button-icon {
        width: 24px;
        height: 24px;
        margin-right: 6px;

        object-fit: contain;
    }

    .button-kind-highlighted {
        outline: 0px;
        background-color: white;
        color: #00c3ff;
    }
    .button-kind-border {
        background-color: transparent !important;
        outline-color: rgba(0, 0, 0, 0.1) !important;
        border: 1px solid rgba(0, 0, 0, 0.35);
        color: black;
        font-weight: normal;
    }
    .theme-dark.button-kind-border,
    :global(body.penguinmodsvelteui-theme-dark) .button-kind-border {
        outline-color: rgba(255, 255, 255, 0.1) !important;
        border: 1px solid rgba(255, 255, 255, 0.35);
        color: white;
    }
</style>
