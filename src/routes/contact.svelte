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
</style>

<svelte:head>
	<title>Contact Us</title>
</svelte:head>

<div class="statement">
    <h2 class="scream">Contact Us</h2>
	<p>Email: info@qubit.com.ng</p>
	<Button>Whatsapp &nbsp; <i class="fa fa-whatsapp" style="font-size:24px;color:green"></i></Button>
</div>