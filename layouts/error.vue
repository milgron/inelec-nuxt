<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404">La página que estás buscando no se encuentra disponible.</h1>
    <h1 v-else>Algo sucedió. Por favor, volvé a la home.</h1>
    <div class="link-wrapper">
      <nuxt-link to="/">Volver al inicio</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'default'
}
</script>

<style lang="scss" scoped>
  .container {
    padding: 4rem;
    text-align: center;
  }
  .link-wrapper {
    margin-top: 3rem;
  }
  a {
    color: inherit;
    text-decoration: none;
    font-size: 1.6rem;
  }
</style>