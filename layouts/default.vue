<template>
  <div>
    <Header/>
    <div class="content">
      <nuxt />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from '../components/Header'
import Footer from '../components/Footer'
export default {
  components: {
    Header, Footer
  }
}
</script> 
<style>
.content {
  margin-top: -16rem;
}

@media screen and (min-width: 920px) {
  .content {
    margin-top: 0;
  }
}
</style>
