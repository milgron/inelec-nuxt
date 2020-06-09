<template>
  <div class="single-product-wrapper">
    <div class="image-wrapper">
      <img :src="img_url" alt="">
    </div>
    <div class="data-wrapper">
      <div class="title-wrapper">
        <p class="title">
          {{title}}
        </p>
      </div>
      <div class="data-list-wrapper">
        <ul class="data-list">
          <div v-if="codes">
            <li class="data-item">
              <strong>Models: </strong>
              {{codes}}
            </li>
          </div>
          <!-- <li class="data-item">
            <strong>Gas: </strong>
            Zone: 0, 1 and 2
          </li>
          <li class="data-item">
            <strong>Dust: </strong>
            Zone: 20, 21 and 22
          </li>
          <li class="data-item">
            <strong>Power: </strong>
            Rechargeable
          </li>
          <li class="data-item">
            <strong>Light: </strong>
            LED
          </li> -->
        </ul>
      </div>
      <div class="logos-wrapper">
        <img src="/icons-product.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      title: String,
      codes: String,
      id: Number
    },
    data () {
      return {
        img_url: ''
      }
    },
    async fetch() {
      const id = this.id
      const url = "https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/products?per_page=100";
      let products = await this.$http.$get(url);
      
      const product = products.filter(singleProduct => {
        if(singleProduct.id === id) {
          return singleProduct
        }
      })
      const imgId = await product[0].featured_media
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

.sub-categories-wrapper {
  margin: 1rem 0;
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 2rem;
}

.single-product-wrapper {
  background-color: $orange;
  display: flex;
  flex-direction: column;
  margin: 2rem 0;
}

.image-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  padding: 2rem;

  img {
    max-width: 300px;
  }
}

.data-wrapper {
  flex: 1 1;
  padding: 2rem;
  background-color: $light-gray;
}

.title-wrapper {
  .title{
    font-weight: bold;
    font-size: 2rem;
  }
}

.data-list-wrapper {
  margin-top: 1rem;
  
  .data-list {
    .data-item {
  text-transform: none;
      font-size: 1.8rem;
    }
  }
}

.logos-wrapper {
  display: flex;
  flex-direction: row;
  margin-top: 2rem;
  max-width: 20rem;
  
  img {
    width: 100%;
  }
}

@media screen and (min-width: 920px) {
  .single-product-wrapper {
    flex-direction: row;
  }
}

</style>