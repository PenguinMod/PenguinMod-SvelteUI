<script>
    import { page } from "$app/state";

    import * as PenguinModSvelteUI from "$lib/index.js";

    const switchTheme = (theme) => {
        const searchParams = page.url.searchParams;
        searchParams.set("theme", theme);
        location.href = String(page.url);
    };
</script>

<button onclick={() => switchTheme("light")}>Light</button>
<button onclick={() => switchTheme("dark")}>Dark</button>

<h1>Button</h1>
<PenguinModSvelteUI.Button>
    Button
</PenguinModSvelteUI.Button>
<br>
<PenguinModSvelteUI.Button link="https://example.com">
    Link
</PenguinModSvelteUI.Button>
<PenguinModSvelteUI.Button link="https://example.com" noredirect>
    Link noredirect
</PenguinModSvelteUI.Button>
<br>
<PenguinModSvelteUI.Button kind="border">
    kind border
</PenguinModSvelteUI.Button>
<PenguinModSvelteUI.Button kind="highlighted">
    kind highlighted
</PenguinModSvelteUI.Button>
<br>
<PenguinModSvelteUI.Button icon="/favicon.svg">
    Icon
</PenguinModSvelteUI.Button>
<br>
<PenguinModSvelteUI.Button theme="dark">
    Theme Dark
</PenguinModSvelteUI.Button>
<br>
<PenguinModSvelteUI.Button color="red">
    Red
</PenguinModSvelteUI.Button>
<PenguinModSvelteUI.Button color="gold">
    Gold
</PenguinModSvelteUI.Button>
<PenguinModSvelteUI.Button color="#ff00ff">
    #ff00ff
</PenguinModSvelteUI.Button>
<PenguinModSvelteUI.Button color="rgb(0, 255, 0)">
    rgb(0, 255, 0)
</PenguinModSvelteUI.Button>
<br>
<PenguinModSvelteUI.Button kind="highlighted" color="#ff00ff">
    kind highlighted + color #ff00ff
</PenguinModSvelteUI.Button>
<PenguinModSvelteUI.Button theme="dark" kind="border">
    Theme Dark + kind border
</PenguinModSvelteUI.Button>