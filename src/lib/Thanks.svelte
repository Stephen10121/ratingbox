<script lang="ts">
    import PrettyBox from "./PrettyBox.svelte";

    export let selected: string | number;
</script>

<PrettyBox centered>
    <div class="thanks-icon">
        <img src="/illustration-thank-you.svg" alt="Thank you svg icon.">
    </div>
    <div class="rating-given">
        <p>You selected {selected} out of 5</p>
    </div>
    <h1>Thank You!</h1>
    <p class="darker">We appreciate you taking the time to give us a rating. If you ever need more support, don't hesitate to get in touch!</p>
</PrettyBox>

<style>
    .thanks-icon {
        height: 110px;
    }
    .rating-given p {
        font-family: 'Overpass', sans-serif;
        font-weight: 400;
        font-size: 15px;
        color: hsl(25, 97%, 53%);
        background-color: hsla(216, 12%, 54%, 0.192);
        padding: 5px 15px;
        border-radius: 100vh;
        padding-top: 8px;
    }

    h1 {
        font-family: 'Overpass', sans-serif;
        font-weight: 700;
        color: #ffffff;
    }

    .darker {
        font-family: 'Overpass', sans-serif;
        font-weight: 400;
        font-size: 15px;
        color: hsl(217, 12%, 63%);
    }
</style>