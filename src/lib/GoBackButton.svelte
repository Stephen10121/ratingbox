<script lang="ts">
    import { fade } from 'svelte/transition';
</script>

<button on:click transition:fade title="Go Back"><img src="/arrow-left.svg" alt="Go Back Icon"></button>

<style>
    button {
        position: fixed;
        top: 10px;
        left: 10px;
        width: 45px;
        height: 45px;
        border-radius: 100%;
        background-color: hsla(216, 12%, 54%, 0.192);
        display: flex;
        align-items: center;
        justify-content: center;
        border: none;
        font-family: 'Overpass', sans-serif;
        font-weight: 700;
        font-size: 15px;
        color: #dbdbdb;
        cursor: pointer;
        transition: background-color 0.15s linear;
    }

    button:hover {
        background-color: hsla(216, 12%, 54%, 0.432);
    }
</style>