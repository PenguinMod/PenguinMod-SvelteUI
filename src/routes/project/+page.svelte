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
<PenguinModSvelteUI.Project src="/favicon.png" userSrc="/favicon.png">
    {#snippet textTop()}long textTop AAAAAAAAAAAAAAAAAAAAA{/snippet}
    {#snippet textBottom()}long textBottom AAAAAAAAAAAAAAAAAAAAA{/snippet}
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
    theme="dark"
>
    {#snippet textTop()}Theme dark{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    theme="dark"
    href="https://example.com"
>
    {#snippet textTop()}Theme dark{/snippet}
    {#snippet textBottom()}+ href{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    theme="dark"
    button={true}
>
    {#snippet textTop()}Theme dark{/snippet}
    {#snippet textBottom()}+ button{/snippet}
</PenguinModSvelteUI.Project>
<br />
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    glint={"featured"}
>
    {#snippet textTop()}glint Featured{/snippet}
    {#snippet textBottom()}textBottom{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    glint={"featured"}
    href="https://example.com"
>
    {#snippet textTop()}glint Featured{/snippet}
    {#snippet textBottom()}+ href{/snippet}
</PenguinModSvelteUI.Project>
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    glint={"featured"}
    button={true}
>
    {#snippet textTop()}glint Featured{/snippet}
    {#snippet textBottom()}+ button{/snippet}
</PenguinModSvelteUI.Project>
<br />
<PenguinModSvelteUI.Project
    src="/favicon.png"
    userSrc="/favicon.png"
    glint={"featured"}
    theme="dark"
>
    {#snippet textTop()}Theme dark{/snippet}
    {#snippet textBottom()}+ glint Featured{/snippet}
</PenguinModSvelteUI.Project>