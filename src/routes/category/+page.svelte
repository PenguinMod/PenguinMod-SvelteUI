<script>
    import * as PenguinModSvelteUI from "$lib/index.js";
</script>

<h1>Category</h1>
<PenguinModSvelteUI.Category>
    Category
</PenguinModSvelteUI.Category>
<br />
<PenguinModSvelteUI.Category theme="dark">
    Theme Dark
</PenguinModSvelteUI.Category>
<br />
<PenguinModSvelteUI.Category>
    {#snippet header()}
        header
    {/snippet}
    Snippet Header
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category>
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Snippet HeaderSecondary
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category>
    {#snippet header()}
        header
    {/snippet}
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Snippet Header + Snippet HeaderSecondary
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category>
    {#snippet header()}
        This is an example of see more links
    {/snippet}
    {#snippet headerSecondary()}
        <a href="https://example.com">
            See more
        </a>
    {/snippet}
    See more example
</PenguinModSvelteUI.Category>
<br />
<PenguinModSvelteUI.Category theme="dark">
    {#snippet header()}
        header
    {/snippet}
    Theme Dark + Snippet Header
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category theme="dark">
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Theme Dark + Snippet HeaderSecondary
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category theme="dark">
    {#snippet header()}
        header
    {/snippet}
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Theme Dark + Snippet Header + Snippet HeaderSecondary
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category theme="dark">
    {#snippet header()}
        This is an example of see more links
    {/snippet}
    {#snippet headerSecondary()}
        <a href="https://example.com">
            See more
        </a>
    {/snippet}
    Theme Dark + See more example
</PenguinModSvelteUI.Category>