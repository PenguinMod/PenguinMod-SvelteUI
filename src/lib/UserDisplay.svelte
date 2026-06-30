<script>
    /**
     * @typedef {Object} Properties
     * @property {string?} src Image src to display
     * @property {string?} alt Image alt to display
     * @property {string?} href A link to redirect to when the display is clicked
     * @property {string?} target Anchor target (for href)
     * @property {"subtext"|"detail"|null} kind The styling of the user display, generally for textBottom
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
            class="userdisplay-textcontainer-top"
            data-penguinmodsvelteui-userdisplay-texttop="true"
        >
            {@render props.textTop()}
        </p>
        <p
            class={"userdisplay-textcontainer-bottom" + (props.kind ? ` userdisplay-textcontainer-bottom-theme-${props.kind}` : " ")}
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
        height: 20px;
        margin-block: 0;

        display: flex;
        flex-direction: row;
        align-items: center;

        font-size: 16px;
        vertical-align: middle;
    }

    .userdisplay-textcontainer-top {
        font-weight: bold;
    }
    .userdisplay-textcontainer-bottom-theme-detail {
        opacity: 0.7;
        font-style: italic;
    }
</style>
