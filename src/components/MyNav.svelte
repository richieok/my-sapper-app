<script>
  let open = false;

  function toggleIcon() {
    open = !open;
  }
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  :root {
    --list-item-h-width: 6rem;
    --list-item-v-width: 8rem;
    --dark-transparent: rgba(0, 0, 0, 0.3);
  }
  nav {
    display: flex;
    height: 65px;
    justify-content: space-between;
    align-items: center;
    background-color: var(--dark-transparent);
    position: relative;
  }
  #logo {
    display: block;
    text-transform: uppercase;
    text-align: center;
    width: 100px;
  }

  .nav-list {
    display: flex;
    position: relative;
    /* max-width: 70%; */
    margin: 0;
  }
  .nav-list li {
    display: flex;
    list-style: none;
    min-width: var(--list-item-h-width);
    min-height: 2rem;
    justify-content: center;
  }

  .nav-list a {
    text-decoration: none;
    padding: 1rem 0rem;
  }

  #nav-icon {
    cursor: pointer;
    display: none;
  }

  #nav-icon div {
    width: 25px;
    height: 3px;
    margin: 5px;
    background-color: white;
    transition: 0.4s;
  }

  #nav-icon.open div:nth-child(1) {
    -webkit-transform: translateY(-8px) rotate(-45deg);
    transform: translateY(8px) rotate(45deg);
    -moz-transform: translateY(8px) rotate(45deg);
  }

  #nav-icon.open div:nth-child(2) {
    opacity: 0;
  }

  #nav-icon.open div:nth-child(3) {
    -webkit-transform: translateY(-8px) rotate(-45deg);
    transform: translateY(-8px) rotate(-45deg);
  }
  nav .active {
    height: 4px;
    width: var(--list-item-h-width);
    background-color: white;
    position: absolute;
    bottom: 0;
    transition: transform 0.6s;
  }

  /* .nav-list li:nth-child(1):hover~.active {
    transform: translateX(0);
  } */

  .nav-list li:nth-child(2):hover~.active {
    transform: translateX(6rem);
  }

  .nav-list li:nth-child(3):hover~.active {
    transform: translateX(12rem);

  }

  .nav-list li:nth-child(4):hover~.active {
    transform: translateX(18rem);
  }

  .nav-list li:nth-child(5):hover~.active {
    transform: translateX(24rem);
  }

  @media only screen and (max-width: 600px) {
    .nav-list {
      /* display: none; */
      flex-direction: column;
      position: absolute;
      top: 65px;
      right: -8rem;
      background-color: var(--dark-transparent);
      z-index: 1;
      transition: right 0.5s;
      -webkit-transition: right 0.5;
    }
    .nav-list li {
      min-width: var(--list-item-v-width);
    }
    #nav-icon {
      display: inline-block;
    }
    .vertical {
      right: 0px;
    }
    nav .active {
      display: none;
    }
  }
</style>

<nav>
  <div id="logo"><img src="qubit_480_white.png" height="65px" alt=""></div>
  <ul class={open ? 'nav-list vertical' : 'nav-list'}>
    <li>
      <a href=".">Home</a>
    </li>
    <li>
      <a href="/webdesign">Webdesign</a>
    </li>
    <li>
      <a href="/contact">Contact Us</a>
    </li>
    <!-- <li>
      <a href="/register">Signup</a>
    </li>
    <li>
      <a href="/logout">Logout</a>
    </li> -->
    <div class="active" />
  </ul>
  <div id="nav-icon" class={open ? 'open' : ''} on:click={toggleIcon}>
    <div />
    <div />
    <div />
  </div>
</nav>
