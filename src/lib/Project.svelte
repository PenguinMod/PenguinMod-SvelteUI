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
     * @property {"subtext"|"detail"|null} kind The styling of the project element, generally for user display
     */
    /** @type {Properties} */
    const props = $props();
</script>

{#snippet container()}
    <div class="project-container">
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
                kind={props.kind}
            />
        </div>
    </div>
{/snippet}
<div
    {...props}
    class="project"
    data-glint={props.glint}
    data-penguinmodsvelteui-project="true"
>
    {#if props.href}
        <a
            href={props.href}
            target={props.target}
            class="project-href"
            data-penguinmodsvelteui-project-href="true"
        >
            {@render container()}
        </a>
    {:else if props.button}
        <button
            class="project-button"
            data-penguinmodsvelteui-project-button="true"
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
        width: 204px;
        height: 204px;
        padding: 8px 8px 2px;
        margin: 4px;
        border-width: 1px;

        border-radius: 4px;
        border-style: solid;
        border-color: #0000001a;
    }
</style>
