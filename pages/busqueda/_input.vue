<template>
  <div class="main-wrapper">
    <div class="main-title">Resultados para {{this.$route.params.input}}</div>
    <div v-if="!searchDone" class="state-text">Buscando resultados...</div>
    <div v-else>
      <div v-if="products.length > 0">
        <div v-for="product in products" :key="product.id">
          <nuxt-link :to="product.route">
            <div class="product-wrapper">
              <div class="title">
                {{product.title}}
              </div>
              <div class="product-category">{{product.category}}</div>
            </div>
          </nuxt-link>
        </div>
      </div>
      <div v-else class="state-text">No se encontraron resultados</div>
    </div>
  </div>
</template>

<script>
  export default {
    data() { 
      return {
        input: this.$route.params.input,
        products: [],
        searchDone: false
      }
    },
    async beforeMount() {
      let categories;
      await this.$axios.get("https://data.inelecsafety.com.ar/wp-json/wp/v2/categories?per_page=100")
      .then(response => {
        categories = response.data.map(category => {
          return {
            id: category.id,
            name: category.name,
            parent: category.parent
          }
        })
      })
      await this.$axios.get("https://data.inelecsafety.com.ar/wp-json/wp/v2/products?per_page=100")
      .then(response => {
        let allProducts = response.data.map(product => {
          let category_name = ""
          switch (product.categories[0]) {
            case 2:
              category_name = "Iluminación portatil"
              break;
            case 4:
              category_name = "Accesorios"
              break;
            case 3:
              category_name = "Iluminación temporal"
              break;
            default:
              break;
          }
          return {
            id: product.id,
            title: product.title.rendered,
            category: category_name,
            route: `/product/${product.id}`
          }
        })

        let filteredProducts = allProducts.filter(product => { 
          let input = this.$route.params.input.toLowerCase()
          let title = product.title.toLowerCase()

          if(title.includes(input)) {
            return product
          }
        })
        this.products = filteredProducts
      })
      this.searchDone = true
    }
  }
</script>

<style lang="scss" scoped>
.main-title {
  font-size: 2.4rem;
}
.main-wrapper {
  padding: 2rem;
}
a {
  text-decoration: none;
  color: inherit;
}
.product-wrapper {
  padding: 2rem;
  border: 1px solid black;
  background: #fff; 
  margin: 1rem 0;
  display: flex;
  flex-direction: row;
  align-items: center;

  .title {
    font-size: 1.6rem;
  }
}

.state-text {
  font-size: 1.6rem;
}

.product-category {
  background: #000;
  color: #fff;
  padding: 1rem;
  margin-left: 2rem;
}
</style>