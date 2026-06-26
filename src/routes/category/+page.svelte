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
<br />
<PenguinModSvelteUI.Category>
    Snippet Footer
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category>
    Snippet Footer with big content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<br />
<PenguinModSvelteUI.Category theme="dark">
    Theme Dark + Snippet Footer
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category theme="dark">
    Theme Dark + Snippet Footer with big content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<br />
<PenguinModSvelteUI.Category>
    {#snippet header()}
        header
    {/snippet}
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Snippet Header + Snippet HeaderSecondary + Snippet Footer
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category>
    {#snippet header()}
        header
    {/snippet}
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Snippet Header + Snippet HeaderSecondary + Snippet Footer with big content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<br />
<PenguinModSvelteUI.Category theme="dark">
    {#snippet header()}
        header
    {/snippet}
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Theme Dark + Snippet Header + Snippet HeaderSecondary + Snippet Footer
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<PenguinModSvelteUI.Category theme="dark">
    {#snippet header()}
        header
    {/snippet}
    {#snippet headerSecondary()}
        headerSecondary
    {/snippet}
    Theme Dark + Snippet Header + Snippet HeaderSecondary + Snippet Footer with big content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    <br />
    Content
    {#snippet footer()}
        footer
    {/snippet}
</PenguinModSvelteUI.Category>
<br />
<div style="display: grid;grid-auto-flow: column;justify-items: start;">
    <PenguinModSvelteUI.Category>
        Lined up categories
    </PenguinModSvelteUI.Category>
    <PenguinModSvelteUI.Category>
        {#snippet header()}
            Lined up categories (header)
        {/snippet}
        {#snippet headerSecondary()}
            headerSecondary
        {/snippet}
        Lined up categories
    </PenguinModSvelteUI.Category>
    <PenguinModSvelteUI.Category>
        Lined up categories
        {#snippet footer()}
            footer
        {/snippet}
    </PenguinModSvelteUI.Category>
    <PenguinModSvelteUI.Category>
        {#snippet header()}
            Lined up categories (header)
        {/snippet}
        {#snippet headerSecondary()}
            headerSecondary
        {/snippet}
        Lined up categories
        {#snippet footer()}
            footer
        {/snippet}
    </PenguinModSvelteUI.Category>
</div>