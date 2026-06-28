<script>
    import * as PenguinModSvelteUI from "$lib/index.js";
</script>

<h1>SwappableHolder</h1>
<PenguinModSvelteUI.SwappableHolder>
    {#snippet holderFirst()}
        holderFirst
    {/snippet}
    {#snippet holderSecond()}
        holderSecond
    {/snippet}
    {#snippet swapFirst()}{/snippet}
    {#snippet swapSecond()}{/snippet}
</PenguinModSvelteUI.SwappableHolder>
<PenguinModSvelteUI.SwappableHolder>
    {#snippet holderFirst()}
        holderFirst
    {/snippet}
    {#snippet holderSecond()}
        holderSecond
    {/snippet}
    {#snippet swapFirst()}
        swapFirst
    {/snippet}
    {#snippet swapSecond()}
        swapSecond
    {/snippet}
</PenguinModSvelteUI.SwappableHolder>
<br />
<PenguinModSvelteUI.SwappableHolder>
    {#snippet holderFirst()}
        First Long content Long content Long content Long content Long content Long content
    {/snippet}
    {#snippet holderSecond()}
        Second Long content Long content Long content Long content Long content Long content
    {/snippet}
    {#snippet swapFirst()}
        swapFirst
    {/snippet}
    {#snippet swapSecond()}
        swapSecond
    {/snippet}
</PenguinModSvelteUI.SwappableHolder>
<br />
<PenguinModSvelteUI.SwappableHolder>
    {#snippet holderFirst()}
        <PenguinModSvelteUI.Category>
            {#snippet header()}
                Category 1
            {/snippet}
            Category example (1)
        </PenguinModSvelteUI.Category>
    {/snippet}
    {#snippet holderSecond()}
        <PenguinModSvelteUI.Category>
            {#snippet header()}
                Category 2
            {/snippet}
            Category example (2)
        </PenguinModSvelteUI.Category>
    {/snippet}
    {#snippet swapFirst()}
        swapFirst
    {/snippet}
    {#snippet swapSecond()}
        swapSecond
    {/snippet}
</PenguinModSvelteUI.SwappableHolder>