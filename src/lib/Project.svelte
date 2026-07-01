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
     * @property {boolean?} featured Whether or not to apply the featured project glint
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
    data-featured={props.featured}
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

</style>
