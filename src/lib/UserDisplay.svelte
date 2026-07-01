<script>
    /**
     * @typedef {Object} Properties
     * @property {string?} src Image src to display
     * @property {string?} alt Image alt to display
     * @property {string?} href A link to redirect to when the display is clicked
     * @property {string?} target Anchor target (for href)
     * @property {"subtext"|"detail"|"note"|null} kind The styling of the user display, generally for textBottom
     */
    /** @type {Properties} */
    const props = $props();
</script>

{#snippet display()}
    {#if props.src}
        <img
            src={props.src}
            alt={props.alt}
        />
    {/if}
    <div class="userdisplay-textcontainer">
        <p
            class={"userdisplay-textcontainer-top" + (props.kind ? ` userdisplay-textcontainer-top-kind-${props.kind}` : " ")}
            data-penguinmodsvelteui-userdisplay-texttop="true"
        >
            {@render props.textTop()}
        </p>
        <p
            class={"userdisplay-textcontainer-bottom" + (props.kind ? ` userdisplay-textcontainer-bottom-kind-${props.kind}` : " ")}
            data-penguinmodsvelteui-userdisplay-textbottom="true"
        >
            {@render props.textBottom()}
        </p>
    </div>
{/snippet}
<div
    {...props}
    class="userdisplay"
    data-penguinmodsvelteui-userdisplay="true"
>
    {#if props.href}
        <a
            href={props.href}
            target={props.target}
            class="userdisplay-href"
            data-penguinmodsvelteui-userdisplay-href="true"
        >
            {@render display()}
        </a>
    {:else}
        {@render display()}
    {/if}
</div>

<style>
    .userdisplay {
        height: 40px;

        display: flex;
        flex-direction: row;
    }
    .userdisplay-href {
        /* ideally dont let the *whole* width of the userdisplay be an <a> element */
        height: 100%;
        
        display: flex;
        flex-direction: row;

        color: inherit;
        text-decoration: none;
    }

    .userdisplay img {
        width: 40px;
        height: 40px;
        margin-right: 4px;

        border-radius: 4px;
    }
    :global(html[dir="rtl"]) .userdisplay img {
        margin-right: initial;
        margin-left: 4px;
    }
    .userdisplay-textcontainer {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    }
    .userdisplay-textcontainer p {
        margin-block: 0;

        font-size: 16px;
        vertical-align: middle;
        text-overflow: ellipsis;
        white-space: nowrap;
        overflow: hidden;
    }

    .userdisplay-textcontainer-top {
        height: 20px;
        
        vertical-align: bottom;
        
        line-height: 20px;
        font-size: 18px !important;
        font-weight: bold;
    }
    .userdisplay-textcontainer-top-kind-note {
        height: 24px;
        line-height: 24px;
    }
    .userdisplay-textcontainer-bottom {
        height: 20px;
        
        vertical-align: top;

        line-height: 20px;
    }
    .userdisplay-textcontainer-bottom-kind-detail {
        opacity: 0.7;
        font-style: italic;
    }
    .userdisplay-textcontainer-bottom-kind-note {
        height: 16px;
        line-height: 16px;

        opacity: 0.7;
        font-weight: bold;
        font-size: 14px !important;
    }
</style>
