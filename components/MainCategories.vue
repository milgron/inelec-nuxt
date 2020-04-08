<template>
  <div>
    <div class="products-wrapper">
      <div class="single-product-wrapper">
        <div class="image-wrapper">
          image
        </div>
        <TitleWrapper 
          title="Lorem ipsum"
          color="#FFF"
          backgroundColorString="dark-gray"
        />
        <div class="description-wrapper">
          <div class="copy">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis officiis ab impedit! Ratione, porro distinctio.
          </div>
        </div>
      </div>
      <div class="single-product-wrapper">
        <div class="image-wrapper">
          image
        </div>
        <TitleWrapper 
          title="Lorem ipsum"
          color="#FFF"
          backgroundColorString="dark-gray"
        />
        <div class="description-wrapper">
          <div class="copy">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis officiis ab impedit! Ratione, porro distinctio.
          </div>
        </div>
      </div>
      <div class="single-product-wrapper">
        <div class="image-wrapper">
          image
        </div>
        <TitleWrapper 
          title="Lorem ipsum"
          color="#FFF"
          backgroundColorString="dark-gray"
        />
        <div class="description-wrapper">
          <div class="copy">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis officiis ab impedit! Ratione, porro distinctio.
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
    }
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';
.products-wrapper {
  padding: 2rem;
  background: $orange;
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 3rem;
}

.single-product-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 1rem 0;
}

.description-wrapper {
  .copy {
    color: #fff;
    text-align: centeR;
  }
}

@media screen and (min-width: 920px) {
  .products-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}

</style>