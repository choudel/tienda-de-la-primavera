<script>
  let selected = "start";
  let toggle = false;
  let page_1 = [
    "page_1 Items_1",
    "page_1 Items_2",
    "page_1 Items_3",
    "page_1 Items_4",
    "page_1 Items_5",
  ];
  let page_2 = [
    "page_2 Items_1",
    "page_2 Items_2",
    "page_2 Items_3",
    "page_2 Items_4",
    "page_2 Items_5",
  ];
  let page_3 = [
    "page_3 Items_1",
    "page_3 Items_2",
    "page_3 Items_3",
    "page_3 Items_4",
    "page_3 Items_5",
  ];
  let page_4 = [
    "page_4 Items_1",
    "page_4 Items_2",
    "page_4 Items_3",
    "page_4 Items_4",
    "page_4 Items_5",
  ];
</script>

<nav
  class="nav-bar"
  id="start"
  style="
    --color1:#44746c;
    --color2:#66876c;
    --color3:#91986e;
    --color4:#c1a57b"
>
  <div class="first_accordion">
    <input
      class="first_accordion__input"
      type="checkbox"
      name="first_accordion"
      id="section1"
    />
    <label class="first_accordion__label" for="section1"> Flip button</label>
    <a href="/" class="logo1"
      ><img src="/favicon.png" alt="elsensei" width="50" height="50" /></a
    >

    <div class="first_accordion__content">
      <div class="second_accordion">
        <a href="/" class="login">Login</a>
        <a href="/" class="logo"
          ><img src="/favicon.png" alt="alt logo" width="50" height="50" /></a
        >
        <a href="/" class="home">Accueil</a>

        <input
          class="second_accordion__input"
          type="radio"
          name="second_accordion"
          id="page_1"
          value="ser"
          bind:group={selected}
          on:click={selected != "ser" || !toggle
            ? () => (toggle = true)
            : () => (toggle = !toggle)}
        />
        <label class="second_accordion__label" for="page_1" id="page_1_id"
          >page_1</label
        >

        <div
          class="second_accordion__content"
          id="page_1__content"
          class:toggle={!toggle}
        >
          <div class="sub_page_1">
            {#each page_1 as detail}
              <a href="/elsensei-fr/page_1">{detail}</a>
            {/each}
          </div>
        </div>

        <input
          class="second_accordion__input"
          type="radio"
          name="second_accordion"
          id="page_2"
          value="tor"
          bind:group={selected}
          on:click={selected != "tor" || !toggle
            ? () => (toggle = true)
            : () => (toggle = !toggle)}
        />
        <label class="second_accordion__label" for="page_2" id="page_2_id"
          >page_2</label
        >

        <div
          class="second_accordion__content"
          id="page_2__content"
          class:toggle={!toggle}
        >
          <div class="sub_page_2">
            {#each page_2 as detail}
              <a href="/elsensei-fr/page_2">{detail}</a>
            {/each}
          </div>
        </div>

        <input
          class="second_accordion__input"
          type="radio"
          name="second_accordion"
          id="page_3"
          value="tee"
          bind:group={selected}
          on:click={selected != "tee" || !toggle
            ? () => (toggle = true)
            : () => (toggle = !toggle)}
        />
        <label class="second_accordion__label" for="page_3" id="page_3_id"
          >page_3</label
        >

        <div
          class="second_accordion__content"
          id="page_3__content"
          class:toggle={!toggle}
        >
          <div class="sub_page_3">
            {#each page_3 as detail}
              <a href="/elsensei-fr/page_3">{detail}</a>
            {/each}
          </div>
        </div>

        <input
          class="second_accordion__input"
          type="radio"
          name="second_accordion"
          id="page_4"
          value="cer"
          bind:group={selected}
          on:click={selected != "cer" || !toggle
            ? () => (toggle = true)
            : () => (toggle = !toggle)}
        />
        <label class="second_accordion__label" for="page_4" id="page_4_id"
          >page_4</label
        >

        <div
          class="second_accordion__content"
          id="page_4__content"
          class:toggle={!toggle}
        >
          <div class="sub_page_4">
            {#each page_4 as detail}
              <a href="/elsensei-fr/page_4">{detail}</a>
            {/each}
          </div>
        </div>

        <a href="/page_5" class="blog">Page_5</a>
      </div>
    </div>
  </div>
  <div class="test" class:toggle={!toggle} on:click={() => (toggle = false)}>
    {!toggle ? "" : "close"}
  </div>
</nav>

<style lang="scss">
  $break: 815px;
  $color_fr: #44746c;
  $color_en: #325e66;
  $color_ar: #2f4858;
  $height: 4vh;
  //first nav
  .nav-bar {
    color: white;
    min-height: $height;
    font-family: "Lexend Deca", sans-serif;
    font-family: "Noto Sans Arabic", sans-serif;
  }
  a {
    color: whitesmoke;
    text-align: center;
    text-decoration: none;
    padding: 10px 10px;
  }
  .toggle {
    height: 0px;
  }
  .test {
    background-color: var(--color4);
    text-align: center;
    border-radius: 0 0 5px 5px;
    cursor: pointer;
  }
  .first_accordion {
    min-height: $height;
    box-shadow: 0 0 10px rgba($color: var(--color1), $alpha: 1);
    border-radius: 5px 5px;
    overflow: hidden;
    background: var(--color1);
    display: grid;
    grid-template-areas:
      "logo1 button"
      "coll coll";
    grid-template-columns: 100px auto;
  }
  .first_accordion__input {
    display: none;
    background-color: var(--color2);
    @media only screen and (max-width: $break) {
      &:checked ~ .first_accordion__content {
        display: grid;
      }
    }
  }
  .first_accordion__label {
    display: none;
    grid-area: button;
    cursor: pointer;
    padding: 10px;
    @media only screen and (max-width: $break) {
      display: grid;
      text-align: right;
    }
  }
  .first_accordion__content {
    font-size: 1rem;
    display: grid;
    text-align: center;
    grid-area: coll;
    @media only screen and (max-width: $break) {
      display: none;
    }
  }
  .logo1 {
    display: none;
    grid-area: logo1;
    @media only screen and (max-width: $break) {
      display: grid;
      text-align: left;
    }
  }
  .second_accordion {
    align-items: center;
    border-radius: 5px;
    overflow: hidden;
    background: var(--color1);
    display: grid;
    grid-template-areas:
      "logo home page_1 mentor mentee certif blog . login "
      "ser ser ser ser ser ser ser ser ser"
      "tors tors tors tors tors tors tors tors tors"
      "tees tees tees tees tees tees tees tees tees"
      "cer cer cer cer cer cer cer cer cer";
    grid-template-columns: 100px 100px 100px 100px 100px 100px 100px auto 100px;
    @media only screen and (max-width: $break) {
      grid-template-areas:
        "logo"
        "login"
        "home"
        "page_1"
        "ser"
        "mentor"
        "tors"
        "mentee"
        "tees"
        "certif"
        "cer"
        "blog";
      grid-template-columns: auto;
      background-color: var(--color2);
    }
  }
  .second_accordion__input {
    display: none;
    padding: 10px 10px;
    align-items: center;
    justify-items: center;
  }
  .second_accordion__label {
    display: grid;
    cursor: pointer;
    padding: 10px 10px;
  }
  .second_accordion__content {
    text-align: left;
    display: none;
  }
  .second_accordion__content > div {
    display: grid;
    padding: 10px;
  }
  .second_accordion__content > div > a {
    display: grid;
    padding: 10px;
    text-align: left;
  }
  .logo {
    display: grid;
    grid-area: logo;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      display: none;
      background-color: var(--color2);
    }
  }
  .home {
    display: grid;
    min-height: $height;
    align-items: center;
    justify-items: center;
    grid-area: home;
    background-color: var(--color1);
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
  .login {
    display: grid;
    grid-area: login;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
  #page_1 {
    &:checked ~ #page_1__content {
      display: grid;
    }
    @media only screen and (max-width: $break) {
      display: none;
      &:checked ~ #page_1__content {
        display: grid;
      }
    }
  }
  #page_1_id {
    display: grid;
    grid-area: page_1;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
  #page_1__content {
    grid-area: ser;
  }
  .sub_page_1 {
    background-color: var(--color3);
  }
  #page_2 {
    &:checked ~ #page_2__content {
      display: grid;
    }
    @media only screen and (max-width: $break) {
      display: none;
      &:checked ~ #page_2__content {
        display: grid;
      }
    }
  }
  #page_2_id {
    display: grid;
    grid-area: mentor;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
  #page_2__content {
    grid-area: tors;
  }
  .sub_page_2 {
    background-color: var(--color3);
  }
  #page_3 {
    &:checked ~ #page_3__content {
      display: grid;
    }
    @media only screen and (max-width: $break) {
      display: none;
      &:checked ~ #page_3__content {
        display: grid;
      }
    }
  }
  #page_3_id {
    display: grid;
    grid-area: mentee;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
  #page_3__content {
    grid-area: tees;
  }
  .sub_page_3 {
    background-color: var(--color3);
  }
  #page_4 {
    &:checked ~ #page_4__content {
      display: grid;
    }
    @media only screen and (max-width: $break) {
      display: none;
      &:checked ~ #page_4__content {
        display: grid;
      }
    }
  }
  #page_4_id {
    display: grid;
    grid-area: certif;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
  #page_4__content {
    grid-area: cer;
  }
  .sub_page_4 {
    background-color: var(--color3);
  }
  .blog {
    display: grid;
    grid-area: blog;
    background-color: var(--color1);
    min-height: $height;
    align-items: center;
    justify-items: center;
    @media only screen and (max-width: $break) {
      background-color: var(--color2);
    }
  }
</style>
