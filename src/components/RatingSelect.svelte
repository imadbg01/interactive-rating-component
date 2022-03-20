<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  let selected;

  const onChange = (e) => {
    selected = e.currentTarget.value;
  };

  const handleSubmit = (e) => {
    if (!selected) return;
    dispatch("rating-select", selected);
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <ul class="rating">
    <li>
      <input
        type="radio"
        value="1"
        id="num1"
        name="rating"
        on:change={onChange}
        checked={selected === 1}
      />
      <label for="num1">1</label>
    </li>
    <li>
      <input
        type="radio"
        value="2"
        id="num2"
        name="rating"
        on:change={onChange}
        checked={selected === 2}
      />
      <label for="num2">2</label>
    </li>
    <li>
      <input
        type="radio"
        value="3"
        id="num3"
        name="rating"
        on:change={onChange}
        checked={selected === 3}
      />
      <label for="num3">3</label>
    </li>
    <li>
      <input
        type="radio"
        value="4"
        id="num4"
        name="rating"
        on:change={onChange}
        checked={selected === 4}
      />
      <label for="num4">4</label>
    </li>
    <li>
      <input
        type="radio"
        value="5"
        id="num5"
        name="rating"
        on:change={onChange}
        checked={selected === 5}
      />
      <label for="num5">5</label>
    </li>
  </ul>
  <button type="submit">submit</button>
</form>

<style>
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
    width: 100%;
  }

  .rating {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 1rem 0;
    transition: background-color 250ms ease-in-out, color 300ms ease-in-out;
  }

  li {
    background-color: hsl(216, 12%, 8%);
    width: 5rem;
    height: 5rem;
    border-radius: 50%;
    position: relative;
    cursor: pointer;
  }
  .rating li:hover,
  .rating li:focus {
    background-color: hsl(25, 97%, 53%);
    color: hsl(0, 0%, 100%);
  }

  input[type="radio"] {
    width: 100%;
    height: 100%;
    opacity: 0;
    appearance: none;
  }

  label {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
    cursor: pointer;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }
  [type="radio"]:checked ~ label,
  [type="radio"]:focus ~ label {
    background: hsl(217, 12%, 63%);
    color: hsl(0, 0%, 100%);
  }
  button[type="submit"] {
    border: none;
    outline: none;
    width: 100%;
    padding: 1em;
    border-radius: 2rem;
    font: inherit;
    font-size: 1.75rem;
    font-weight: 700;
    cursor: pointer;
    background-color: hsl(25, 97%, 53%);
    color: hsl(0, 0%, 100%);
    transition: background-color 250ms ease-in-out, color 300ms ease-in-out;
  }

  button[type="submit"]:hover,
  button[type="submit"]:focus {
    background-color: hsl(0, 0%, 100%);
    color: hsl(25, 97%, 53%);
  }
</style>
