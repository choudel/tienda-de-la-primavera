<script lang="ts">
  import SecondAccordion from "./second_accordion.svelte";
</script>

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
    <SecondAccordion />
  </div>
</div>

<style lang="scss">
  $break: 815px;
  $color_fr: #44746c;
  $color_en: #325e66;
  $color_ar: #2f4858;
  $height: 4vh;
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
</style>
