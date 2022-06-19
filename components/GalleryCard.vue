<template>
    <div class="gallery-card">
        <nuxt-link :to="href">
            <div>
                <img :src="img" :alt="title"/>
            </div>
        </nuxt-link>
        <div>
            <h4>{{title}}</h4>
            <p>{{info}}</p>
        </div>
        <div>
            <Button />
        </div>
    </div>
</template>

<style lang="scss">


</style>

<script>
import Button from './Button'

export default {
  name: 'GalleryCard',
  components: {
    Button
  },
  props: [
        "title",
        "href",
        "img",
        "info",
        "id"
  ]
}
</script>