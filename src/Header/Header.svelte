<header>
  <a href="#"><img src="images/logo.svg" alt="Logo" /></a>
  <nav id="menu">
    <ul>
      <li><a href="#">Features</a></li>
      <li><a href="#">Pricing</a></li>
      <li><a href="#">Resources</a></li>
      <span class="line"></span>
      <li class="auto-left"><a href="#">Login</a></li>
      <li class="cyan"><a href="#">Sign Up</a></li>
    </ul>
  </nav>
  <a href="#main-menu-toggle" class="backdrop" hidden></a>
  <a id="menu-toggle" class="hamburger" href="#menu">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="#000000"
      viewBox="0 0 50 50"
      width="40px"
      height="45px"
    >
      <path
        d="M 0 7.5 L 0 12.5 L 50 12.5 L 50 7.5 Z M 0 22.5 L 0 27.5 L 50 27.5 L 50 22.5 Z M 0 37.5 L 0 42.5 L 50 42.5 L 50 37.5 Z"
      />
    </svg>
  </a>
</header>

<style>
  header {
    display: flex;
  }

  header > a {
    margin-right: 45px;
  }

  .line,
  .hamburger {
    display: none;
  }

  nav {
    flex: 1 0 auto;
  }

  ul {
    display: flex;
  }

  li ~ li {
    margin-left: 30px;
  }

  li.auto-left {
    margin-left: auto;
  }

  li a {
    color: var(--grayishViolet);
  }

  li.cyan a {
    border: 0;
    border-radius: 20px;
    background-color: var(--cyan);
    padding: 10px 30px;
    color: var(--white);
  }

  @media screen and (max-width: 1339px) {
    header {
      position: relative;
      align-items: center;
      justify-content: space-between;
    }

    header > a {
      margin-right: 0;
    }

    .line {
      margin: 0 auto;
      margin-top: 20px;
      display: block;
      width: 90%;
      height: 3px;
      background-color: var(--grayishViolet);
    }

    #menu {
      max-width: 650px;
      z-index: 10;
      display: none;
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      bottom: -240px;
      width: 90%;
      border-radius: 10px;
      background-color: var(--dark-violet);
    }

    ul {
      flex-direction: column;
      text-align: center;
    }

    li ~ li {
      margin-left: 0;
    }

    li {
      margin-top: 20px;
    }

    li.auto-left {
      margin-left: 0;
    }

    li a {
      margin-top: 10px;
      color: var(--white);
    }

    .hamburger {
      display: block;
    }

    #menu:target {
      display: block;
    }

    #menu:target ~ .backdrop {
      display: block;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 5;
      background-color: rgba(0, 0, 0, 0.1);
      cursor: default;
    }

    header {
      display: flex;
    }

    li.cyan {
      width: 100%;
      margin-bottom: 35px;
    }

    li.cyan a {
      width: 100%;
      padding: 10px 95px;
    }
  }
</style>
