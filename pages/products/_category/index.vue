<template>
  <div class="main-wrapper">
    <TitleWrapper
      :title="category"
      backgroundColorString="#EF7C00"
      color="#202020"
    />
    <hr>
    <div class="copy-wrapper">
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p>
    </div>
    <div class="sub-categories-wrapper">
      <nuxt-link :to="'/products/'+category+'/testing'">
        <div class="single-sub-category-wrapper">
          <div class="image-wrapper">
            <img src="/test-product.jpg" alt="">
          </div>
          <div class="title-wrapper">
            <p class="title">
              Category
            </p>
          </div>
        </div>
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/testing'">
        <div class="single-sub-category-wrapper">
          <div class="image-wrapper">
            <img src="/test-product.jpg" alt="">
          </div>
          <div class="title-wrapper">
            <p class="title">
              Category
            </p>
          </div>
        </div>
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/testing'">
        <div class="single-sub-category-wrapper">
          <div class="image-wrapper">
            <img src="/test-product.jpg" alt="">
          </div>
          <div class="title-wrapper">
            <p class="title">
              Category
            </p>
          </div>
        </div>
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/testing'">
        <div class="single-sub-category-wrapper">
          <div class="image-wrapper">
            <img src="/test-product.jpg" alt="">
          </div>
          <div class="title-wrapper">
            <p class="title">
              Category
            </p>
          </div>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../../../components/TitleWrapper'
  export default {
    components: {
      TitleWrapper
    },
    data() {
      return {
        category: ''
      }
    },
    mounted() {
      const category = this.$route.params.category
      const replacedCategory = category.replace('-',' ')
      this.category = replacedCategory
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