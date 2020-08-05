<script>
  export let image;
  export let title;
  export let description;
  export let top;
</script>

<div class="card" style="top: {top ? top : '0px'}">
  <div class="image-container">
    <img src="{image}" alt="Brand Recognition" />
  </div>
  <h4>{title}</h4>
  <p>
    {description}
  </p>
</div>

<style>
  .card {
    background-color: var(--white);
    width: 350px;
    position: relative;
    z-index: 2;
    padding: 70px 20px 0 20px;
    border-radius: 5px;
  }

  h4,
  p {
    text-align: left;
  }

  p {
    margin-top: 20px;
    margin-bottom: 35px;
  }

  .image-container {
    position: absolute;
    top: -33px;
    left: 7%;
    width: 70px;
    padding: 14px 18px;
    border-radius: 50%;
    background-color: var(--dark-violet);
  }

  img {
    width: 100%;
  }

  @media screen and (max-width: 1339px) {
    .card {
      width: 320px;
    }

    .image-container {
      left: 50%;
      transform: translateX(-50%);
    }
  }
</style>
