<script>
    import * as cssColor from "@asamuzakjp/css-color";

    /**
     * @typedef {Object} Properties
     * @property {string?} href A link to redirect to when the button is clicked
     * @property {string?} target Anchor target (for href)
     * @property {"highlighted"|"border"|null} kind The style for the button's look
     * @property {string?} icon An image URL to put next to the button
     * @property {"dark"|null} theme Forces a specific theme
     * @property {string?} color CSS color for the button
     */
    /** @type {Properties} */
    const props = $props();
    let href = $derived(props.href);
    let target = $derived(props.target);

    // style
    let kind = $derived(props.kind);
    let icon = $derived(props.icon);
    let theme = $derived(props.theme);
    let color = $derived(props.color);

    let colorStyle = $state(``);
    let outlineColor = $state(`rgba(0, 195, 255, 0.35)`);
    const updated = () => {
        if (color) {
            switch (kind) {
                case "highlighted":
                    colorStyle = `color:${color};`
                    break;
                default:
                    colorStyle = `background-color:${color};`
                    break;
            }
            if (!kind) {
                const resolved = cssColor.resolve(color);
                const hex = cssColor.convert.colorToHex(resolved, { alpha: false });

                outlineColor = hex + "59";
            }
        }
    };
    updated();
    $effect(updated);
</script>

{#snippet button()}
    <button
        {...props}
        data-penguinmodsvelteui-button="true"
        class={`button${kind ? ` button-kind-${kind}` : ""}${theme ? ` theme-${theme}` : ""} ${props.class || ""}`}
        style={`${colorStyle}outline-color:${outlineColor};${props.style || ""}`}
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
{#if href}
    <a
        href={href}
        target={target}
        style="text-decoration: none;"
        data-penguinmodsvelteui-button-href="true"
    >
        {@render button()}
    </a>
{:else}
    {@render button()}
{/if}

<style>
    .button {
        margin: 4px;
        padding: 1rem 1rem;
        
        font-weight: 600;
        font-size: 1.1rem;
        border: 0px;
        border-radius: 4px;
        outline-width: 2px;
        outline-style: solid;
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
    :global(html[dir="rtl"]) .button-icon {
        margin-right: initial;
        margin-left: 6px;
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
