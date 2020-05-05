<template>
  <div class="parent-container">
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
  .parent-container {
    background: #ddd;
  }
  .content {
    margin-top: 0;
  }
}
@media screen and (min-width: 1500px) {
  .content {
    width: calc(100vw - 10%);
    margin-top: 10rem;
    max-width: 140rem;
    margin: auto;
    padding: 2rem 0;

  }
}
</style>
