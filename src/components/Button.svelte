<script>
    export let text = '';
    export let href = '#';
</script>

<style>
  .button {
    text-decoration: none;
    border: 2px solid white;
    margin: auto;
    color: white;
    text-transform: uppercase;
    padding: 1rem 2rem;
    position: relative;
    transition: color 0.5s;
    overflow: hidden;
    /* z-index: 1; */
  }

  .button:hover {
      color: black;
  }

  .button::before {
      content: '';
      position: absolute;
      left: -14px;
      top: 0px;
      width: 0;
      height: 100%;
      background-color: white;
      transform: skewX(25deg);
      transition: width .5s;
      z-index: -1;
  }

  .button:hover::before {
      width: 120%;
  }
</style>

<a {href} class="button">
  <slot></slot>
</a>
