<script>
  import { fade, fly } from "svelte/transition";

  import SectionRating from "./components/SectionRating.svelte";
  import SectionThankYou from "./components/SectionThankYou.svelte";

  let isSelect = false;

  let rating;
  const handleSelect = (e) => {
    rating = e.detail;
    isSelect = true;
  };
</script>

<main>
  {#if !isSelect}
    <SectionRating on:rating-select={handleSelect} />
  {:else}
    <div transition:fly={{ delay: 350, duration: 450 }}>
      <SectionThankYou selected={rating} />
    </div>
  {/if}
</main>

<style>
  main {
    display: grid;
    justify-content: center;
    gap: 2rem;
  }
</style>
