<script>
    /**
     * @typedef {Object} Properties
     * @property {string} src Image src to display
     * @property {string?} alt Image alt to display
     * @property {string?} href A link to redirect to when the display is clicked
     * @property {string?} target Anchor target (for href)
     */
    /** @type {Properties} */
    const props = $props();
</script>

{#snippet display()}
    <img
        src={props.src}
        alt={props.alt}
    />
    <div class="userdisplay-textcontainer">
        <p
            class="userdisplay-textcontainer-top"
            data-penguinmodsvelteui-userdisplay-texttop="true"
        >
            User text
        </p>
        <p
            class="userdisplay-textcontainer-bottom"
            data-penguinmodsvelteui-userdisplay-textbottom="true"
        >
            Bottom text
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
        width: 100%;
        height: 48px;

        display: flex;
        flex-direction: row;
    }
    .userdisplay-href {
        width: 100%;
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

        background-color: red;
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
</style>
