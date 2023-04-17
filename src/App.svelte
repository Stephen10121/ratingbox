<script lang="ts">
  import GoBackButton from "./lib/GoBackButton.svelte";
  import PrettyBox from "./lib/PrettyBox.svelte";
  import { fade } from 'svelte/transition';
  import Rating from "./lib/Rating.svelte";
  import Thanks from "./lib/Thanks.svelte";

  let ratingSubmitted = false;
  let rating: string;

  function submittedRating({ detail }: { detail: string }) {
    rating = detail;
    ratingSubmitted = true;
  }
</script>

{#if ratingSubmitted}
  <GoBackButton on:click={() => ratingSubmitted=false} />
{/if}

<PrettyBox heightPx={382}>
  {#if ratingSubmitted}
    <section out:fade={{duration: 100}} in:fade={{delay: 100, duration: 100}} style="align-items: center;">
      <Thanks selected={rating} />
    </section>
  {:else}
    <section out:fade={{duration: 100}} in:fade={{delay: 100, duration: 100}}>
      <Rating selected={rating} on:submit={submittedRating} />
    </section>
  {/if}
</PrettyBox>

<style>
  section {
    position: absolute;
    top: 0;
    left: 0;
    height: 382px;
    width: 100%;
    display: flex;
    padding: 30px;
    gap: 25px;
    flex-direction: column;
    justify-content: center;
  }
</style>