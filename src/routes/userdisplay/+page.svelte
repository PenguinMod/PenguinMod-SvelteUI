<script>
    import * as PenguinModSvelteUI from "$lib/index.js";
</script>

<h1>UserDisplay</h1>
<PenguinModSvelteUI.UserDisplay>
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.UserDisplay>
<br />
<PenguinModSvelteUI.UserDisplay src="/favicon.png">
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.UserDisplay>
<br />
<PenguinModSvelteUI.UserDisplay src="/favicon.png" kind="subtext">
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom Kind subtext{/snippet}
</PenguinModSvelteUI.UserDisplay>
<PenguinModSvelteUI.UserDisplay src="/favicon.png" kind="detail">
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom Kind detail{/snippet}
</PenguinModSvelteUI.UserDisplay>
<br />
<PenguinModSvelteUI.UserDisplay src="/favicon.png" href="https://example.com/">
    {#snippet textTop()}href{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.UserDisplay>
<PenguinModSvelteUI.UserDisplay src="/favicon.png" href="https://example.com/" target="_blank">
    {#snippet textTop()}href + target{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.UserDisplay>
<br />
<PenguinModSvelteUI.UserDisplay src="/favicon.png" href="https://example.com/" kind="subtext">
    {#snippet textTop()}href{/snippet}
    {#snippet textBottom()}textBottom Kind subtext{/snippet}
</PenguinModSvelteUI.UserDisplay>
<PenguinModSvelteUI.UserDisplay src="/favicon.png" href="https://example.com/" kind="detail">
    {#snippet textTop()}href{/snippet}
    {#snippet textBottom()}textBottom Kind detail{/snippet}
</PenguinModSvelteUI.UserDisplay>