<template>
  <section id="projects" class="grid-container padding">
    <div class="grid-inner">
      <div class="projects-header">
        <h2>Design</h2>
        <p class="display-font">
          Made with a passion for design and adventure.
        </p>
      </div>
      <div class="padding">
        <h3 class="projects-subheader">
          Online Course Design
        </h3>
        <div class="projects-design">
          <GalleryCard
            v-for="galleryCard in galleryCards"
            :key="galleryCard.id"
            :title="galleryCard.title"
            :info="galleryCard.subtitle"
            :link="galleryCard.link"
            :img="galleryCard.img"
          >
          </GalleryCard>
        </div>
      </div>
      <div class="padding-less">
        <h3 class="projects-subheader">
          Explorations
        </h3>
        <div class="projects-table">
          <ArticleTable
            v-for="post in posts"
            :key="post.id"
            :colorBg="post.colorBg"
            :title="post.title"
            :subtitle="post.subtitle"
            :info="post.info"
            :link="post.link"
          >
          </ArticleTable>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
    export default {
      name: 'Projects',
      data() {
        return {
          galleryCards: [
            {
              id: '1',
              title: 'Example ',
              info: 'Some info',
              img: '/imgs/projects/tst1.jpg',
              link: "/"
            },
            {
              id: '2',
              title: 'Example',
              info: 'Some info',
              img: '/imgs/projects/tst2.jpg',
              link: "/"
            },
            {
              id: '3',
              title: 'Example',
              info: 'Some info',
              img: '/imgs/projects/tst1.jpg',
              link: "/"
            },
          ],
          posts: [
            {
              id: '1',
              colorBg: 'var(--light)',
              title: 'Meet the Phantom 3 Pro',
              subtitle: 'Augumented Reality',
              info: 'Marketing app that advertises a drone using UI, model animation, planar detection and portals.',
              link: "/"
            },
            {
              id: '2',
              colorBg: 'var(--accent-primary)',
              title: 'Construction Site',
              subtitle: 'Virtual Reality',
              info: 'Explore a construction site using teleportation, object interaction, and environment creation.',
              link: "/"
            },
            {
              id: '3',
              colorBg: 'var(--light)',
              title: 'Save the Crew',
              subtitle: 'Vanilla Javascript',
              info: 'Back to basics with Rock-Paper-Scissors (Lizard, Spock): practicing JS logic, dom manipulation and canvas exploration.',
              link: "/"
            }
          ]
        }
      }
    }  
</script>

<style lang="scss">

  .projects-header {
    text-align: center;
    p {
      font-size: 24px;
    }
  }

  .projects-design {
    display: flex;
  }

  .projects-table {
    border: 2px solid var(--dark);
    height: auto;
    width: auto;
  }

</style>