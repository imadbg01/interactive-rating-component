<script>
  export let selected;
</script>

<section>
  <figure>
    <img src="./images/illustration-thank-you.svg" alt="Thankyou" />
  </figure>
  <div>
    <p class="summary">You selected {selected} out of 5</p>
  </div>
  <h2 class="heading">Thank you!</h2>
  <p class="paragraph">
    We appreciate you taking the time to give a rating. If you ever need more
    support, don’t hesitate to get in touch!
  </p>
</section>

<style>
  section {
    text-align: center;
    align-items: center;
  }
  .summary {
    background-color: hsl(216, 12%, 8%);
    color: hsl(25, 97%, 53%);
    padding: 1em 1.5em;
    border-radius: 2.5rem;
  }
</style>
