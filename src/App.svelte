<script lang="ts">
  import GoBackButton from "./lib/GoBackButton.svelte";
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

{#if ratingSubmitted}
  <Thanks selected={rating} />
{:else}
  <Rating selected={rating} on:submit={submittedRating} />
{/if}