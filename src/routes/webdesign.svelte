<style>
  :root {
    --dark-transparent: rgba(0, 0, 0, 0.5);
  }

  .statement {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    max-width: 500px;
    text-align: center;
    background-color: var(--dark-transparent);
    padding: 2rem 1rem;
    border-radius: 20px;
    overflow: auto;
    margin: auto;
  }

  .statement p {
    padding: 20px 40px;
    margin: 0;
  }
  .scream {
    text-transform: uppercase;
  }
</style>

<svelte:head>
  <title>Web Design</title>
</svelte:head>

<div class="statement">
  <h2 class="scream">Web Design</h2>
  <p>
    We are web application developers providing a suite of services to enhance
    your business growth and productivity. We build secure online services
    optimized to perform efficiently and reliably.
  </p>
</div>
