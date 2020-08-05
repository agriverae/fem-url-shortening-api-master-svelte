<article>
  <div class="text-info">
    <h1>More than just shorter links</h1>
    <p>
      Build your brand’s recognition and get detailed insights on how your links
      are performing.
    </p>
    <button class="cyan">Get Started</button>
  </div>
  <img src="images/illustration-working.svg" alt="Woman working" />
</article>

<style>
  article {
    display: flex;
    place-items: center;
    padding-right: 0;
    position: relative;
    overflow: hidden;
    padding-bottom: 120px;
  }

  .text-info {
    margin-top: 15px;
  }

  h1 {
    font-size: 2.8rem;
    line-height: 4rem;
  }

  p {
    font-size: 1.2rem;
    line-height: 1.6rem;
    margin-bottom: 30px;
  }

  img {
    position: relative;
    left: 8%;
    width: 60%;
  }

  @media screen and (max-width: 1339px) {
    article {
      flex-direction: column;
    }

    .text-info {
      order: 1;
      text-align: center;
    }
  }
</style>
