<script>
    import * as PenguinModSvelteUI from "$lib/index.js";
</script>

<h1>UserDisplay</h1>
<PenguinModSvelteUI.UserDisplay src="/favicon.png">
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.UserDisplay>
<br />
<PenguinModSvelteUI.UserDisplay src="/favicon.png" href="https://example.com/">
    {#snippet textTop()}href (textTop){/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.UserDisplay>