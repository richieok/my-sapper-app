<script>
  import MyNav from "../components/MyNav.svelte";

  // export let segment;
</script>

<style>
  /* main {
    position: relative;
    max-width: 56em;
    padding: 2em;
    margin: 0 auto;
  } */
  main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 80vh;
  }
  img {
    position: fixed;
    z-index: -1;
    opacity: 0.3;
    left: 0;
    top: 0;
    height: auto;
    min-width: 720px;
    min-height: 100%;
    width: 100%;
  }
  @media screen and (max-width: 720px) {
    img {
      left: 50%;
      margin-left: -360px;
    }
  }
</style>

<img src="asphalt-road-720.jpg" alt="" />
<MyNav />

<main>
  <slot />
</main>
