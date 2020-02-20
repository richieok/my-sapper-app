<script>
  import Button from "../components/Button.svelte";
</script>

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
  }
  .scream {
    text-transform: uppercase;
  }
  .fade {
    animation-name: fade;
    animation-duration: 1.5s;
  }
  @keyframes fade {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>

<svelte:head>
  <title>Qubit Home</title>
</svelte:head>

<div class="statement fade">
  <h2 class="scream">Connect your Business</h2>
  <p>
    Let’s help you take your business online.
    <br />
    We design full stack web servers in the cloud that keep your business and
    service always available to you and your clients from anywhere in the world.
  </p>
  <Button href="/login">Learn More</Button>
  <!-- <a href="/webdesign" class="button">Learn more</a> -->
</div>
