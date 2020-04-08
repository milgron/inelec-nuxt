<template>
  <div>
    <MainProductsWrapper />
    <WeAreBar />
    <MainCategories />
    <BlogPosts />
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
    }
  }
</script>

<style lang="scss" scoped>
  
</style>