<script>
  let focus = false;

  function handleFocus() {
    focus = true;
  }

  function handleBlur() {
    focus = false;
  }
</script>

<div class="wrapper" class:shake={focus}>
  <input
    class="search-bar"
    placeholder="Search any Pokémon"
    on:focus={handleFocus}
    on:blur={handleBlur}
  />
</div>

<style>
  /* your styles go here */
  @keyframes shake {
    0% {
      transform: rotate(0deg);
    }
    10% {
      transform: rotate(-2deg);
    }
    20% {
      transform: rotate(0deg);
    }
    30% {
      transform: rotate(2deg);
    }
    40% {
      transform: rotate(0deg);
    }
    55% {
      transform: rotate(-4deg);
    }
    70% {
      transform: rotate(0deg);
    }
    85% {
      transform: rotate(4deg);
    }
    100% {
      transform: rotate(0deg);
    }
  }

  .shake::before {
    animation: shake 0.8s infinite;
  }

  .wrapper {
    position: relative;
  }

  .wrapper::before {
    position: absolute;
    content: url(/pokeball.svg);
    top: 0.5rem;
    left: 0.7rem;
    width: 1.5rem;
    height: 1.5rem;
  }

  .search-bar {
    font-size: 1rem;
    outline: none;
    border: 0.25rem solid black;
    border-radius: 1rem;
    height: 2rem;
    padding: 0 1rem 0 2.5rem;
    max-width: 20rem;
  }
</style>
