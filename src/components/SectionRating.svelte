<script>
  import RatingSelect from "./RatingSelect.svelte";
  let iconStart = "images/icon-star.svg";
</script>

<section>
  <figure>
    <img src={iconStart} alt="start" />
  </figure>
  <h1 class="heading">How did we do?</h1>
  <p class="paragraph">
    Please let us know how we did with your support request. All feedback is
    appreciated to help us improve our offering!
  </p>
  <RatingSelect on:rating-select />
</section>

<style>
  figure {
    background-color: hsl(216, 12%, 8%);
    height: 5rem;
    width: 5rem;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  @media (max-width: 29rem) {
    section {
      max-width: 90%;
      margin: auto;
    }
  }
</style>
