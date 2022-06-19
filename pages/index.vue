<template>
  <div class="grid-none"> 
    <Header :anchorLink="Header.anchorLink" />
    <About />
    <Contact />
  </div>
</template>

<script>
  export default {
    name: 'IndexPage',
    data() {
        return {
            Header: {
              anchorLink:'#about' 
            }
        }
    }
  }
</script>

<style lang="scss">
  #about {
    width: 100%;
    background-color: var(--about);
  }
</style>