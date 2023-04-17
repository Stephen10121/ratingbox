<script lang="ts">
    export let centered = false;
</script>

<section style="{centered ? "align-items: center;" : ""}">
    <slot />
</section>

<style>
    section {
        width: 375px;
        display: flex;
        padding: 30px;
        gap: 25px;
        flex-direction: column;
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