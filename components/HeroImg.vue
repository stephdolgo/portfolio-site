<template>
    <div class="grid-outer parallax parallax-hero"></div>
</template>

<style lang="scss">
  .parallax-hero {
    background-image: url("static/brand/hero-jungle.jpg");
    min-height: 100vh; 
    opacity: 0.25;
    cursor: none;
  }
</style>

<script>
    export default {
        name: 'HeroImg',  
    }
</script>