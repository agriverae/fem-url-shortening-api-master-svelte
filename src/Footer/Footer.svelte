<footer>
  <img class="logo" src="images/logo-white.svg" alt="logo" />
  <div class="info">
    <h5>Features</h5>
    <ul>
      <li><a href="#">Link Shortening</a></li>
      <li><a href="#">Branded Links</a></li>
      <li><a href="#">Analytics</a></li>
    </ul>
  </div>
  <div class="info">
    <h5>Resources</h5>
    <ul>
      <li><a href="#">Blog</a></li>
      <li><a href="#">Developers</a></li>
      <li><a href="#">Support</a></li>
    </ul>
  </div>
  <div class="info">
    <h5>Company</h5>
    <ul>
      <li><a href="#">About</a></li>
      <li><a href="#">Our Team</a></li>
      <li><a href="#">Careers</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </div>
  <div class="icons">
    <img src="images/icon-facebook.svg" alt="facebook" />
    <img src="images/icon-twitter.svg" alt="twitter" />
    <img src="images/icon-pinterest.svg" alt="pinterest" />
    <img src="images/icon-instagram.svg" alt="instagram" />
  </div>
</footer>

<style>
  footer {
    display: grid;
    background-color: var(--darkViolet);
    color: var(--white);
    grid-template-columns: 1fr 200px 200px 200px 1fr;
    padding-top: 50px;
    padding-bottom: 80px;
  }

  footer .logo {
    margin-left: 30%;
  }

  footer .info h5 {
    font-size: 0.9rem;
    margin-bottom: 15px;
  }

  footer .info ul li a {
    font-size: 0.9rem;
    color: var(--grayishViolet);
    margin-top: 5px;
  }

  footer .icons img {
    margin-left: 20px;
  }

  @media screen and (max-width: 1339px) {
    footer {
      justify-content: center;
      grid-template-columns: auto;
      text-align: center;
      padding-bottom: 40px;
    }

    footer .logo {
      margin: 0 auto;
    }

    footer .info h5 {
      margin: auto;
      margin-top: 30px;
      margin-bottom: 15px;
    }

    footer .icons {
      margin-top: 30px;
    }

    footer .icons img {
      cursor: pointer;
    }
  }
</style>
