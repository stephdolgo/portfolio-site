<template>
    <div>

    </div>
</template>

<script>
import Button from './Button'

export default {
  name: 'ArticleTable',
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