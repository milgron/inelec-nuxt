<template>
  <div class="main-wrapper">
    <div class="header-wrapper">
      <TitleWrapper 
        title="Novedades - Blog"
        color="#FFF"
        background="dark-gray"
      />
    </div>
    <div class="news-wrapper">
      <div v-for="post in posts" :key="post.id">
        <div class="post-wrapper">
          <div class="image-wrapper">
            <img :src="post.featured_media" alt="">
          </div>
          <div class="date-wrapper">
            <span class="date">{{post.date}}</span>
          </div>
          <h2 class="post-title">{{post.title.rendered}}</h2>
          <!-- <div class="excerpt-wrapper">
            <div class="copy" v-html="`${post.excerpt.rendered.substring(0,100)} [...]`"></div>
          </div> -->
          <div class="read-more-wrapper">
            <div class="copy">
              <nuxt-link :to="`/blog/${post.id}`">
                Read more
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>


    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../components/TitleWrapper'
  export default {
    components: {
      TitleWrapper
    },
    props: {
      posts: Array,
    },
    data() {
      return {
        media: []
      }
    },
    beforeMount() {
      this.$axios.get("https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/media")
      .then(response => {
        this.media = response.data.filter(post => {
          if(post.id == 115) return post;
        })
      })
    }
        
  }
</script>

<style lang="scss" scoped>
  .main-wrapper {
    padding: 5rem;
    background: #fff;
  }
  .header-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }
  .news-wrapper {
    margin: 1rem 0;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 3rem;
  }
  .image-wrapper {
    margin-bottom: 3rem;

    img {
      width: 100%;
    }
  }
  .excerpt-wrapper {
    .copy {
      font-size: 2rem;
    }
  }
  .read-more-wrapper {
    margin-top: 2rem;

    .copy {
      font-weight: 700;
      font-size: 1.6rem;
      text-transform: uppercase;
    }

    a {
      text-decoration: none;
      color: inherit;
    }
  }

  .post-title {
    font-size: 1.8rem;
  }
  .date-wrapper {
    margin-bottom: 2rem;

    .date {
    background: #202020;
    color: #fff;
    padding: 1rem;
    font-size: 1.4rem;

    }
  }

@media screen and (min-width: 920px) {
  .news-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>