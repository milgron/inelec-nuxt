<template>
  <div>
    <div class="products-wrapper">
      <div class="single-product-wrapper">
        <div class="image-wrapper">
          <img src="/main-categories-1.png" alt="">
        </div>
        <div class="copy-wrapper">
          <TitleWrapper 
            title="portable lighting"
            color="#FFF"
            backgroundColorString="dark-gray"
          />
          <div class="description-wrapper">
            <div class="copy">
  handlamps, torches and headtorches          </div>
          </div>
        </div>
      </div>
      <div class="single-product-wrapper">
        <div class="image-wrapper">
          <img src="/main-categories-2.png" alt="">
        </div>
        <div class="copy-wrapper">
          <TitleWrapper 
            title="temporary lighting"
            color="#FFF"
            backgroundColorString="dark-gray"
          />
          <div class="description-wrapper">
            <div class="copy">
  Luminaires, floodlites, tank lighting kits, handheld
  leadlamps, worklites, airlamps and warning lamps.          </div>
          </div>
        </div>
      </div>
      <div class="single-product-wrapper">
        <div class="image-wrapper">
          <img src="/main-categories-3.png" alt="">
        </div>
        <div class="copy-wrapper">
          <TitleWrapper 
          title="temporary power distribution"
          color="#FFF"
          backgroundColorString="dark-gray"
        />
        <div class="description-wrapper">
          <div class="copy">
Transformers, splitter boxes, cable reels and
extension cables.          </div>
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
  padding: 5rem;
  background: $orange;
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 3rem;
}

.single-product-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  margin: 1rem 0;
  height: 30rem;
}

.description-wrapper {
  .copy {
    color: #fff;
    text-align: centeR;
  }
}

.copy-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;

  .copy {
    font-size: 1.6rem;
  }
}

.image-wrapper {
  margin-bottom: 3rem;
}

@media screen and (min-width: 920px) {
  .products-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}

</style>