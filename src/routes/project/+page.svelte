<script>
    import * as PenguinModSvelteUI from "$lib/index.js";
</script>

<h1>Project</h1>
<PenguinModSvelteUI.Project src="/favicon.png">
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project src="/favicon.png" userSrc="/favicon.png">
    {#snippet textTop()}textTop{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<br />
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    href="https://example.com"
>
    {#snippet textTop()}Href test{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    href="https://example.com"
    target="_blank"
>
    {#snippet textTop()}Href test{/snippet}
    {#snippet textBottom()}+ _blank target{/snippet}
</PenguinModSvelteUI.Project>
<br />
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    button={true}
>
    {#snippet textTop()}Button test{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<br />
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    featured={true}
>
    {#snippet textTop()}Featured project{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    featured={true}
    href="https://example.com"
>
    {#snippet textTop()}Featured project{/snippet}
    {#snippet textBottom()}+ href{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    featured={true}
    button={true}
>
    {#snippet textTop()}Featured project{/snippet}
    {#snippet textBottom()}+ button{/snippet}
</PenguinModSvelteUI.Project>