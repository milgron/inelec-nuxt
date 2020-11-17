<template>
  <div class="main-wrapper">
    <TitleWrapper
      :title="category.name"
      backgroundColorString="orange"
      color="#202020"
    />
    <hr>
    <div class="sub-categories-wrapper">
      <nuxt-link :to="`/product/${product.id}`" v-for="product in products" :key="product.id">
        <SubcategorySingleProduct 
          :title="product.title.rendered"
          :codes="product.acf.codes"
          :id="product.id"
        />
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
        products: []
      }
    },
    beforeMount() {
      const category = this.$route.params.category
      const replacedCategory = category.replace('%20',' ')
      this.category = replacedCategory
      const subcategory = this.$route.params.subCategory
      const replacedSubcategory = subcategory.replace('-',' ')
      this.subCategory = replacedSubcategory
    },
    async fetch() {
      const id = parseInt(this.$route.params.subCategory)
      let products = await this.$http.$get(
        "https://data.inelecsafety.com.ar/wp-json/wp/v2/products?per_page=100"
      );
      let categories = await this.$http.$get(
        "https://data.inelecsafety.com.ar/wp-json/wp/v2/categories?per_page=100"
      );
      this.products = await products.filter(product => {
        if(product.categories.includes(id)) {
          return product
        }
      })
      this.category = await categories.filter(category => {
        return category.id == id
      })[0]
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