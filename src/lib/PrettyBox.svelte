<script lang="ts">
    export let centered = false;
    export let heightPx: number = null;
</script>

<section style="{centered ? "align-items: center;" : ""}{heightPx ? `height: ${heightPx}px`:""}">
    <slot />
</section>

<style>
    section {
        /* position: absolute;
        top: 0;
        left: 0;
        transform: translate(-50%, -50%); */
        position: relative;
        width: 375px;
        border-radius: 20px;
        background-image: radial-gradient(
            circle 449px at 50.5% -26%,
            rgba(124, 135, 152, 0.479) 0%,
            hsl(213, 19%, 18%) 50%
        );
        background-image: -moz-radial-gradient(
            circle 449px at 50.5% -26%,
            rgba(124, 135, 152, 0.479) 0%,
            hsl(213, 19%, 18%) 50%
        );
        background-image: -webkit-radial-gradient(
            circle 449px at 50.5% -26%,
            rgba(124, 135, 152, 0.479) 0%,
            hsl(213, 19%, 18%) 50%
        );
    }
</style>