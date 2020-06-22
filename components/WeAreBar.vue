<template>
  <div>
    <div class="main-wrapper">
      <div class="copy-wrapper">
        <div class="copy">SOMOS DISTRIBUIDORES DEL FABRICANTE LÍDER MUNDIAL DE ILUMINACIÓN PORTÁTIL Y TEMPORAL DE ÁREAS PELIGROSAS</div>
      </div>
      <div class="icons-wrapper">
        <img src="/icons-inelec.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';
.main-wrapper {
  background: $dark-gray;
  padding: 2rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  
  .copy {
    color: #fff;
    text-transform: uppercase;
    font-size: 2.2rem;
  }
}
.icons-wrapper {
  margin-left: 1.5rem;
}
</style>