<template>
  <div class="main-wrapper">
    <TitleWrapper
      :title="subcategory"
      backgroundColorString="orange"
      color="#202020"
    />
    <hr>
    <div class="copy-wrapper">
      <p class="copy">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?
      </p>
    </div>
    <div class="sub-categories-wrapper">
      <nuxt-link :to="'/products/'+category+'/'+subcategory+'/wolflite-xt-rechargeable-led-handlamp'">
        <SubcategorySingleProduct />
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/'+subcategory+'/wolflite-xt-rechargeable-led-handlamp'">
        <SubcategorySingleProduct />
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/'+subcategory+'/wolflite-xt-rechargeable-led-handlamp'">
        <SubcategorySingleProduct />
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/'+subcategory+'/wolflite-xt-rechargeable-led-handlamp'">
        <SubcategorySingleProduct />
      </nuxt-link>
      <nuxt-link :to="'/products/'+category+'/'+subcategory+'/wolflite-xt-rechargeable-led-handlamp'">
        <SubcategorySingleProduct />
      </nuxt-link>
      
    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../../../../components/TitleWrapper'
  import SubcategorySingleProduct from '../../../../components/SubcategorySingleProduct'
  export default {
    components: {
      TitleWrapper,
      SubcategorySingleProduct
    },
    data() {
      return {
        category: '',
        subCategory: '',
      }
    },
    mounted() {
      const category = this.$route.params.category
      const replacedCategory = category.replace('%20',' ')
      this.category = replacedCategory
      const subcategory = this.$route.params.subCategory
      const replacedSubcategory = subcategory.replace('-',' ')
      this.subcategory = replacedSubcategory
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
  background: #ddd;
}

.copy-wrapper {
  margin: 3rem 0;

  .copy {
    font-size: 2.4rem;
    font-weight: bold;
    text-transform: none;
  }
}

@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 3rem 6rem;
  }
}
</style>