<template>
  <div class="main-wrapper">
    <TitleWrapper
      :title="productTitle"
      backgroundColorString="orange"
      color="#202020"
    />
    <hr>
    <div class="models-wrapper">
      <p class="models">{{productCodes}}</p>
    </div>
    <div class="logos-wrapper">
      <img src="/icons-product.png" alt="">
    </div>
    <div class="image-wrapper">
      <img :src="img_url" alt="">
    </div>
    <div class="copy-wrapper">
      <div v-html="productContent" class="copy"></div>
    </div>

    <div class="download-wrapper">
      <div class="download-icon">
        <img src="/files.png" alt="">
      </div>
      <button class="download-button">
        DESCARGAS Y RECURSOS
      </button>
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
        productTitle: "",
        productContent: "",
        productCodes: "",
        img_url: ""
      }
    },
    async fetch() {
      const products = await this.$http.$get(
        "https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/products?per_page=100"
      );
      const product = products.filter(singleProduct => {
        if(singleProduct.id == this.$route.params.productId) return singleProduct
      })
      this.productTitle = product[0].title.rendered
      this.productContent = product[0].content.rendered
      this.productCodes = product[0].acf.codes
      const imgId = product[0].featured_media
      const media_url = `https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/media?per_page=100`
      let media = await this.$http.$get(media_url);
      const filtered_media = await media.filter(singleMedia => {
        if(singleMedia.id === imgId) {
          return singleMedia
        }
      })
      this.img_url = filtered_media[0].guid.rendered.replace("inelec.local","inelecdata.vidasremotas.xyz")
     }
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';

a {
  text-decoration: none;
  color: inherit;
}
.main-wrapper {
  padding: 3rem;
}

.copy-wrapper {
  margin: 1rem 0;
  .copy {
    font-size: 2.2rem;
    line-height: 1.2;
    text-transform: none;
  }
}

.sub-categories-wrapper {
  margin: 1rem 0;
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 2rem;
}

.single-sub-category-wrapper {
  background-color: $orange;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1rem;
}

.title-wrapper {
  .title{
    font-weight: bold;
    font-size: 1.8rem;
  }
}

.models-wrapper {
  margin: 1rem 0;
  .models {
    font-weight: bold;
  }
}

.logos-wrapper {
  display: flex;
  flex-direction: row;
  margin: 1rem 0;

  .logo {
    width: 30px;
    height: 30px;
    background: #000;
    &:not(:first-child) {
      margin-left: 1rem;
    }
  }
}

.download-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  background: $medium-gray;
  max-width: 28rem;
  padding: 1rem;
    font-size: 2rem;

  .download-icon {
    height: 40px;
    width: 40px;

    img {
      width: 100%;
    }
  }
  .download-button {
    border-radius: 0;
    border: none;
    margin-left: 1rem;
    color: $orange;
    font-size: 1.6rem;
    background: transparent;
    
  }
}

.image-wrapper {
  img {
    width: 100%;
  }
}

@media screen and (min-width: 680px) {
  .sub-categories-wrapper {
    grid-template-columns: 1fr 1fr;
    grid-gap: 2rem;
  }
}
@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 5rem 8rem;
  }
  .sub-categories-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>