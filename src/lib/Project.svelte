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
     * @property {boolean?} featured Whether or not to apply the featured project glint
     * @property {"subtext"|"detail"|null} kind The styling of the project element, generally for user display
     */
    /** @type {Properties} */
    const props = $props();
</script>

{#snippet container()}
    <div class="project-container">
        
    </div>
{/snippet}
<div
    {...props}
    class="project"
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
    {:else}
        {@render container()}
    {/if}
</div>

<style>

</style>
