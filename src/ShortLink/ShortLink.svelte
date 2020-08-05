<script>
  let link = "";
  export let links = [];
  let timer = null;
  let errorMesage = "";
  const resetMessageTimer = (message) => {
    clearTimeout(timer);
    errorMesage = message;
    timer = setTimeout(() => {
      errorMesage = "";
    }, 3000);
  };

  const getShortLinks = async () => {
    if (link === "") {
      resetMessageTimer("Please add a Link");
      return;
    }

    const data = await fetch("https://rel.ink/api/links/", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        url: link,
      }),
    })
      .then((res) => res.json())
      .catch((err) => console.log(err));

    if (!data.hashid) {
      resetMessageTimer(data.url);
      return;
    }

    links = [...links, { ...data, isSelected: false }];
  };
</script>

<div class="short-link">
  <div class="input-data">
    <input class="{errorMesage !== "" ? 'error' : ''}" bind:value="{link}"
    type="text" placeholder="Shorten a link here" name="link" id="link" /> {#if
    errorMesage !== ""}
    <p class="error-message">{errorMesage}</p>
    {/if}
  </div>
  <button on:click="{getShortLinks}" class="cyan rough-edge">
    Shorten It!
  </button>
</div>

<style>
  .short-link {
    background-image: url(/images/bg-shorten-desktop.svg);
    background-size: cover;
    background-color: var(--dark-violet);
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    width: calc(100% - 200px);
    height: 150px;
    padding: 2% 5%;
    top: calc(-150px / 2);
    left: 50%;
    transform: translateX(-50%);
  }

  .input-data {
    display: flex;
    flex-direction: column;
    height: 90%;
    width: 70%;
  }

  p.error-message {
    margin-top: 5px;
    padding-left: 8px;
    color: var(--red);
    font-size: 0.8rem;
    align-self: flex-start;
  }

  input {
    width: 100%;
    height: 100%;
    max-height: 54px;
    padding-left: 15px;
    font-size: 1.1rem;
    border-radius: 10px;
  }

  input.error {
    border: 2px solid var(--red);
  }

  button {
    max-height: 54px;
    margin-left: 20px;
    width: 22%;
    height: 57.5%;
    margin-bottom: 27px;
  }

  button:hover {
    background-color: hsl(180, 61%, 73%);
  }

  button.cyan.rough-edge {
    border-radius: 10px;
  }

  @media screen and (max-width: 1339px) {
    .short-link {
      width: 85%;
      max-width: 700px;
      flex-direction: column;
      padding: 2.5% 2%;
    }

    .input-data {
      width: 90%;
    }

    input {
      height: 37px;
      width: 100%;
    }

    input.error {
      margin-top: 25px;
    }

    button {
      height: 37px;
      width: 90%;
      margin-top: 20px;
      margin-left: 0;
    }
  }
</style>
