<script lang="ts">
    import { createEventDispatcher } from 'svelte';
    import PrettyBox from './PrettyBox.svelte';

    export let selected = "5";
    export let ratingRange: string[] = ["1", "2", "3", "4", "5"];
    const dispatch = createEventDispatcher();

    function onChange(event: Event) {
        //@ts-ignore
        selected = event.currentTarget.value;
    }
</script>

<PrettyBox>
    <div class="star-icon">
        <img src="/ratingbox/icon-star.svg" alt="Star Icon">
    </div>
    <h1>How did we do?</h1>
    <p>Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering.</p>
    <form on:submit|preventDefault = {() => dispatch("submit", selected)}>
        <div class="buttons">
            {#each ratingRange as ratingNumber}
                <input class="sr-only" type="radio" on:change={onChange} name="optionratings" id="option{ratingNumber}" value={ratingNumber} checked={selected===ratingNumber} />
                <label for="option{ratingNumber}">{ratingNumber}</label>
            {/each}
        </div>
        <button>Submit</button>
    </form>
</PrettyBox>

<style>
    .star-icon {
        width: 45px;
        height: 45px;
        border-radius: 100%;
        background-color: hsla(216, 12%, 54%, 0.192);
        display: flex;
        align-items: center;
        justify-content: center;
    }

    h1 {
        font-family: 'Overpass', sans-serif;
        font-weight: 700;
        color: #ffffff;
    }

    p {
        font-family: 'Overpass', sans-serif;
        font-weight: 400;
        font-size: 15px;
        color: hsl(217, 12%, 63%);
    }

    form {
        display: flex;
        gap: 25px;
        flex-direction: column;
    }

    .buttons {
        display: flex;
        width: 100%;
        justify-content: space-between;
    }

    .buttons label {
        width: 45px;
        height: 45px;
        border-radius: 100%;
        background-color: hsla(216, 12%, 54%, 0.192);
        display: flex;
        align-items: center;
        justify-content: center;
        font-family: 'Overpass', sans-serif;
        font-weight: 400;
        font-size: 15px;
        color: #dbdbdb;
        padding-top: 3px;
        cursor: pointer;
        transition: background-color 0.15s linear;
    }

    .buttons label:hover {
        background-color: hsl(216, 12%, 54%);
    }

    .buttons input:checked + label {
        background-color: hsl(25, 97%, 53%);
    }

    button {
        height: 45px;
        border-radius: 100vh;
        border: none;
        cursor: pointer;
        font-family: 'Overpass', sans-serif;
        text-transform: uppercase;
        letter-spacing: 2px;
        font-weight: 400;
        font-size: 15px;
        background-color: hsl(25, 97%, 53%);
        color: #ffffff;
        padding-top: 3px;
        transition: background-color 0.15s linear, color 0.15s linear;
    }

    button:hover {
        background-color: #ffffff;
        color: hsl(25, 97%, 53%);
    }
</style>