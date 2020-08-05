<script>
  import ShortLink from "../ShortLink/ShortLink.svelte";
  import Card from "../Card/Card.svelte"
  let links = [];
  const handleClick = (id) => {
    if(!links[id].isSelected)
      links[id].isSelected = true;
  }
</script>

<article>
  <ShortLink bind:links={links} />
  <div class="links-container">
    {#each links as link, index}
    <div class="link">
      <p class="link-name">{link.url}</p>
      <p class="short-link cyan">https://rel.ink/{link.hashid}</p>
      <button on:click={() => handleClick(index) } class="{link.isSelected? "violet" : "cyan"}">{link.isSelected? "Copied" : "Copy"}</button>
    </div>
    {/each}
  </div>
  <h2>Advanced Statistics</h2>
  <p>
    Track how your links are performing across the web with our advanced
    statistics dashboard.
  </p>
  <div class="cards-container">
    <Card top="-45px" image="images/icon-brand-recognition.svg" title="Brand Recognition" description="Boost your brand recognition with each click. Generic links don’t mean a thing. Branded links help instil confidence in your content."  />
    <Card image="images/icon-detailed-records.svg" title="Detailed Records" description="Gain insights into who is clicking your links. Knowing when and where people engage with your content helps inform better decisions."  />
    <Card top="45px" image="images/icon-fully-customizable.svg" title="Fully Customizable" description="Improve brand awareness and content discoverability through customizable links, supercharging audience engagement."  />
  </div>
</article>

<style>
  article {
    position: relative;
    background-color: lightgrey;
    padding-top: 100px;
    padding-bottom: 50px;
    text-align: center;
  }

  .link ~ .link{
    margin-top: 30px;
  }

  h2 {
    margin-top: 40px;
  }

  .cards-container {
    position: relative;
    margin-top: 150px;
    margin-bottom: 85px;
    display: flex;
    justify-content: space-between;
  }

  .cards-container::after {
    z-index: 1;
    top: 50%;
    position: absolute;
    width: 100%;
    height: 10px;
    display: block;
    content: "";
    background-color: var(--cyan);
  }

  .link {
    padding: 10px 30px;
    display: flex;
    place-items: center;
    background-color: var(--white);
  }

  .link-name {
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
    max-width: 900px;
    margin-right: auto;
  }

  p.cyan {
    color: var(--cyan);
  }

  .link button {
    border-radius: 5px;
    margin-left: 30px;
  }

  .violet {
    color: var(--white);
    background-color: var(--dark-violet);
  }

  .link button.cyan:hover {
    background-color: hsl(180, 61%, 73%);
  }

  @media screen and (max-width: 1339px) {
    article {
      padding-top: 120px;
    }

    .link {
      text-align: left;
      padding: 0;
      margin: 0 auto;
      max-width: 700px;
      flex-direction: column;
    }

    .link > p {
      padding-left: 20px;
      padding-right: 20px;
    }

    .link-name {
      border-bottom: 1px solid var(--grayishViolet);
      margin-bottom: 10px;
      margin-top: 20px;
      width: 100%;
      padding-bottom: 20px;
    }


    .link button {
      margin-bottom: 10px;
      width: 90%;
      max-width: 400px;
      margin-left: 0;
    }

    .short-link {
      align-self: flex-start;
      margin-bottom: 10px;
    }

    .cards-container {
      margin-top: 120px;
      flex-direction: column;
      align-items: center;
    }

    .cards-container::after {
      height: 100%;
      width: 10px;
      top: 0;
    }
  }
</style>
