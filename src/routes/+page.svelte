<script>
    import { page } from "$app/state";

    import * as PenguinModSvelteUI from "$lib/index.js";
</script>

{#each Object.keys(PenguinModSvelteUI) as key}
    <a href={`/${key.toLowerCase()}${page.url.search}`}>{key}</a>
{/each}