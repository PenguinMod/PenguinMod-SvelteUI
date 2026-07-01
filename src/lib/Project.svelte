<script>
    import UserDisplay from './UserDisplay.svelte';

    /**
     * @typedef {Object} Properties
     * @property {string} src Image src to display as thumbnail
     * @property {string?} alt Image alt to display as thumbnail
     * @property {string?} userSrc Image src to display as user
     * @property {string?} userAlt Image alt to display as user
     * @property {string?} href A link to redirect to when the display is clicked
     * @property {string?} target Anchor target (for href)
     * @property {boolean?} button Whether the project is a button or not. Not compatible with href
     * @property {"featured"|null} glint Whether or not to apply a project glint, and what kind
     * @property {"subtext"|"detail"|"note"|null} kind The styling of the project element, generally for user display ("note" by default)
     * @property {"dark"|null} theme Forces a specific theme
     */
    /** @type {Properties} */
    const { onclick, ...props } = $props();
    let theme = $derived(props.theme);
    let kind = $derived(props.kind || "note");
</script>

{#snippet container()}
    <div
        class={`project-container${props.glint ? ` project-glint project-glint-${props.glint}` : ""}${theme ? ` theme-${theme}` : ""}`}
        data-penguinmodsvelteui-project-container="true"
    >
        <img
            src={props.src}
            alt={props.alt}
            class="project-container-thumbnail"
        />
        <div
            class="project-container-userdisplay"
            data-penguinmodsvelteui-project-container-userdisplay="true"
        >
            <UserDisplay
                textTop={props.textTop}
                textBottom={props.textBottom}
                src={props.userSrc}
                alt={props.userAlt}
                kind={kind}
            />
        </div>
    </div>
{/snippet}
<div
    {...props}
    class={`project${theme ? ` theme-${theme}` : ""}`}
    data-glint={props.glint}
    data-penguinmodsvelteui-project="true"
>
    {#if props.href}
        <a
            href={props.href}
            target={props.target}
            class="project-href"
            data-penguinmodsvelteui-project-href="true"
            onclick={onclick}
        >
            {@render container()}
        </a>
    {:else if props.button}
        <button
            class="project-button"
            data-penguinmodsvelteui-project-button="true"
            onclick={onclick}
        >
            {@render container()}
        </button>
    {:else}
        {@render container()}
    {/if}
</div>

<style>
    @keyframes project-glint {
        0% {
            background-position: 0% 0%;
        }
        100% {
            background-position: 100% 100%;
        }
    }

    .project {
        /* width + (8px padding + 1px border) * 2 */
        width: calc(204px + ((8px + 1px) * 2));
        /* thumb height + margin + user disp height + (8px padding + 1px border) * 2 */
        height: calc(152px + 4px + 40px + ((8px + 1px) * 2));
        margin: 4px;
    }
    .project-href,
    .project-button {
        display: block;
        width: 100%;
        height: 100%;
        margin: 0;
        padding: 0;
        border: 0;

        background: transparent;
        text-align: inherit;
        text-decoration: inherit;
        color: inherit;
        /* background: yellow; */

        cursor: pointer;
    }
    .project-container {
        /* same as project width & height but without accounting for self margin & padding & border  */
        width: 204px;
        height: calc(152px + 4px + 40px);
        padding: 8px;
        border-width: 1px;

        display: flex;
        flex-direction: column;
        align-items: flex-start;
        
        border-radius: 4px;
        border-style: solid;
        border-color: #0000001a;
        overflow: hidden;
    }
    .theme-dark.project-container,
    :global(body.penguinmodsvelteui-theme-dark) .project-container {
        border-color: #ffffff4d;
    }
    
    .project-glint {
        color: black;
        border-color: #0000001a !important;
        animation: project-glint 3s ease infinite;
    }
    .project-glint-featured {
        background-color: #ffc400;
        background: linear-gradient(
            145deg,
            rgba(255, 196, 0, 1) 0%,
            rgba(255, 196, 0, 1) 45%,
            rgba(255, 255, 255, 1) 50%,
            rgba(255, 196, 0, 1) 54%,
            rgba(255, 196, 0, 1) 100%
        );
        background-size: 300% 300%;
    }
    
    .project-button:focus .project-container {
        outline-width: 4px;
        outline-style: solid;
        outline-color: #0000001a;
    }
    .project-button:focus .theme-dark.project-container,
    :global(body.penguinmodsvelteui-theme-dark) .project-button:focus .project-container {
        outline-color: #ffffff4d;
    }
    .project-button:focus .project-container.project-glint-featured {
        outline-color: #ffc40080;
    }

    .project-container-thumbnail {
        width: 204px;
        height: 152px;
        margin-bottom: 4px;
        
        object-fit: cover;
        border-radius: 4px;
        /* background: red; */
    }
    .project-container-userdisplay {
        display: block;
        width: 100%;
        height: 40px;

        /* background: lightcoral; */
        text-overflow: ellipsis;
        white-space: nowrap;
        overflow: hidden;
    }
    .project-container-userdisplay :global(div[data-penguinmodsvelteui-userdisplay=true]),
    .project-container-userdisplay :global(div[data-penguinmodsvelteui-userdisplay=true] > div),
    .project-container-userdisplay :global(div[data-penguinmodsvelteui-userdisplay=true] > div p) {
        width: 100%;

        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
</style>
