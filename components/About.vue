<template>
  <section id="about" class="grid-container padding">
    <div class="grid-col--left about-img">
        <img src="/brand/self-portrait.gif">
    </div>
    <div class="grid-col--right">
      <div class="about-content">
        <h2>About</h2>
        <div>
          <p>
            Currently I work for Syracuse University🍊 creating
            style guides, illustrations and graphics for online course development.
          </p>     
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
  #about {
    width: 100%;
    background-color: var(--about);

    .about-img {
      display: flex;
      justify-content: center;
      align-items: center;

      img {
        width: 90%;
        height: auto;
      }
    }

    .about-content {
      margin: 20px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
  }
</style>

<script>
export default {
  name: 'About'
}
</script>
