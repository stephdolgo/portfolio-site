<template>
    <div class="grid-inner post-container" :style="{ 'background-color': colorBg}">
      <ul>
        <li>
          <h3>{{ title }}</h3>
          <p>{{ subtitle }}</p>
        </li>
        <li>{{ info }}</li>
        <li>
          <a :href="link">
            <Button btnStyle="dark-btn post-btn">View Post</Button>
          </a>
        </li>
      </ul>
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
        "id",
        "colorBg",
        "title",
        "subtitle",
        "link",
        "info",
  ]
}
</script>

<style lang="scss">
  .post-container {

    ul {
        height: 6em;
        margin: 0;
        position: relative;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        gap: 30px;

        &:before {
            position: absolute; 
            left: 0;
            bottom: 0;
            content: "";
            display: block;
            width: 100%;
            height: 100%;
            background-color: var(--dark-pink);
            transform-origin: 0 bottom 0;
            transform: scaleY(0);
            transition: .4s ease-out;
          }

        &:hover {

          &:before {
            transform: scaleY(1);
          }

        }

        li {
            position: relative;
        }

        li:nth-child(1) {
            order: 1;
            flex-grow: 1;
            width: 25%; 

            h3, p {
              margin: 0; }

        }

        li:nth-child(2) {
            order: 2;
            flex-grow: 2;
            width: 40%;
        }

        li:nth-child(3) {
            order: 3;
            flex-grow: 1;
            width: 25%;
            padding-left: 20px;
        }
    }

    .post-btn {
      padding: 10px 55px;
      &:hover,
      &:focus {
          box-shadow: inset 15em 0 0 0 var(--accent-primary);
          color: var(--dark);
      }
    }

  }
</style>