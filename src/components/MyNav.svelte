<style>
  nav {
    display: flex;
    height: 8vh;
    justify-content: space-between;
    align-items: center;
    background-color: dimgray;
  }
  #logo {
    display: block;
    text-transform: uppercase;
    text-align: center;
    width: 100px;
  }

  .nav-list {
    display: flex;
    justify-content: space-around;
    width: 40%;
  }
  .nav-list li {
    list-style: none;
  }

  .nav-list a {
    text-decoration: none;
    color: black;
  }
</style>

<nav>
  <div id="logo">Logo</div>
  <ul class="nav-list">
    <li><a href=".">Home</a></li>
    <li><a href="/dashboard">Dashboard</a></li>
    <li><a href="/login">Login</a></li>
    <li><a href="/logout">Logout</a></li>
  </ul>
</nav>
