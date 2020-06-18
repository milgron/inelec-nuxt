<template>
  <div>
    <MainProductsWrapper />
    <WeAreBar />
    <MainCategories />
    <BlogPosts 
      :posts="posts"
    />
  </div>
</template>

<script>
  import MainProductsWrapper from '../components/MainProductsWrapper'
  import WeAreBar from '../components/WeAreBar'
  import MainCategories from '../components/MainCategories'
  import BlogPosts from '../components/BlogPosts'
  export default {
    components: {
      BlogPosts,
      MainCategories,
      WeAreBar,
      MainProductsWrapper
    },
    data() {
      return {
        posts: [],
      }
    },
    beforeMount() {
      let featuredMedia = []
      this.$axios.get("https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/posts")
      .then(response => {
        this.posts = response.data.map(post => {
          return {
            id: post.id,
            title: post.title,
            featured_media: post.better_featured_image.source_url,
            content: post.content,
            excerpt: post.excerpt
          }
        })
      })    
    }
  }
</script>

<style lang="scss" scoped>
  
</style>