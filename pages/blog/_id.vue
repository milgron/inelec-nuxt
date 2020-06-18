<template>
  <div class="main-wrapper">
    <div class="head-wrapper">
      <TitleWrapper 
        :title="post.title"
        backgroundColorString="orange"
        color="#202020"
      />
      <hr>
    </div>
    <div class="image-wrapper">
      <img :src="post.media" alt="">
    </div>
    <div class="copy-wrapper">
      <div class="copy" v-html="post.content"></div>
    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../../components/TitleWrapper'
  export default {
    components: {
      TitleWrapper
    },
    data() {
      return {
        id: this.$route.params.id,
        post: {
          title: '',
          content: '',
          media: ''
        }
      }
    },
    beforeMount() {
      this.$axios.get("https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/posts")
      .then(response => {
        let post = response.data.filter(post => {
          if(post.id == this.id) {
            return this.post = {
              title: post.title.rendered,
              content: post.content.rendered,
              media: post.better_featured_image.source_url
            }
          }
        })
      })
    }
  }
</script>

<style lang="scss" scoped>
.main-wrapper {
  padding: 4rem;
  background-color: #ddd;
  max-width: 120rem;
  margin: auto;
}
.image-wrapper {
  width: 100%;
  padding: 2rem 0;

  img {
    width: 100%;
  }
}
.copy-wrapper {
  margin: 1rem 0;

  .copy-main {
    font-weight: bold;
    font-size: 2.4rem;
    line-height: 1.5;
    letter-spacing: 1px;
  }
  .copy {
    margin: 1rem 0;
    font-size: 2.4rem;
    line-height: 1.5;
    letter-spacing: 1px;
    text-transform: none;
  }
}

@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 5rem 8rem;
  }
}
</style>