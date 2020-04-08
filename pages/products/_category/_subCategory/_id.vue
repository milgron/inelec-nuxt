<template>
  <div class="main-wrapper">
    <TitleWrapper
      :title="productName"
      backgroundColorString="#EF7C00"
      color="#202020"
    />
    <hr>
    <div class="models-wrapper">
      <p class="models">XT1, XT2, XT3</p>
    </div>
    <div class="logos-wrapper">
      <div class="logo"></div>
      <div class="logo"></div>
      <div class="logo"></div>
    </div>
    <div class="image-wrapper">
      <img src="/product-big.jpg" alt="">
    </div>
    <div class="copy-wrapper">
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p><br>
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p><br>
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p><br>
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p><br>
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p><br>
    </div>

    <div class="download-wrapper">
      <div class="download-icon"></div>
      <button class="download-button">
        DESCARGAS Y RECURSOS
      </button>
    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../../../../components/TitleWrapper'
  export default {
    components: {
      TitleWrapper
    },
    data() {
      return {
        productName: ''
      }
    },
    mounted() {
      const productName = this.$route.params.id
      const replacedProductName = productName.replace('-',' ')
      this.productName = replacedProductName
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
    font-size: 1.6rem;
    font-weight: bold;
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

  .download-icon {
    height: 30px;
    width: 30px;
    background: $orange;
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
    padding: 3rem 6rem;
  }
  .sub-categories-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>