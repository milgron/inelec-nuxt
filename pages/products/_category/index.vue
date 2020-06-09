<template>
  <div class="main-wrapper">
    <TitleWrapper :title="category" backgroundColorString="orange" color="#202020" />
    <hr />
    <div class="copy-wrapper">
      <p
        class="copy"
      >Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quisquam, iste asperiores maiores dolorum eveniet commodi laborum provident omnis et impedit distinctio quae, quis aliquid totam natus hic veniam. Rerum, repellendus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos vitae ducimus illum, placeat ipsam saepe nisi expedita, consequatur delectus, enim error dolores facilis autem explicabo culpa libero deserunt? Explicabo, amet?</p>
    </div>
    <div class="sub-categories-wrapper">
      <nuxt-link
        :to="`/products/${category}/${childCategory.id}`"
        v-for="childCategory in childCategories"
        :key="childCategory.id"
      >
        <div class="single-sub-category-wrapper">
          <div class="image-wrapper">
            <img src="/main-product-2.png" alt />
          </div>
          <div class="title-wrapper">
            <p class="title">{{childCategory.category}}</p>
          </div>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import TitleWrapper from "../../../components/TitleWrapper";
export default {
  components: {
    TitleWrapper
  },
  data() {
    return {
      category: "",
      childCategories: []
    };
  },
  mounted() {
    const category = this.$route.params.category;
    const replacedCategory = category.replace("-", " ");
    this.category = replacedCategory;
  },
  async fetch() {
    let categories = await this.$http.$get(
      "http://inelecdata.vidasremotas.xyz/wp-json/wp/v2/categories?per_page=100"
    );
    let filteredCategories = categories.map(category => {
      return {
        id: category.id,
        category: category.name,
        parent: category.parent
      };
    });
    let selectedCategory = this.$route.params.category
      .toLowerCase()
      .replace("-", " ")
      .replace("á", "a")
      .replace("é", "e")
      .replace("í", "i")
      .replace("ó", "o")
      .replace("ú", "u");
    switch (selectedCategory) {
      case "iluminacion temporal":
        this.childCategories = filteredCategories.filter(category => {
          return category.parent == 3;
        });
        break;
      case "iluminacion portatil":
        this.childCategories = filteredCategories.filter(category => {
          return category.parent == 2;
        });
        break;
      case "accesorios":
        this.$router.push("/products/accesorios")
        break;
      default:
        break;
    }
    console.log(childCategories);
  }
};
</script>

<style lang="scss" scoped>
@import "~assets/css/colors";

a {
  text-decoration: none;
  color: inherit;
}
.main-wrapper {
  padding: 3rem;
}

.copy-wrapper {
  margin: 3rem 0;

  .copy {
    font-size: 2.4rem;
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
  padding: 2rem;
  height: 400px;
}

.title-wrapper {
  margin-top: 2rem;
  .title {
    font-weight: bold;
    font-size: 3.2rem;
    text-align: center;
  }
}

@media screen and (min-width: 680px) {
  .sub-categories-wrapper {
    grid-template-columns: 1fr 1fr;
    grid-gap: 3rem;
  }
}
@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 3rem 6rem;
  }
  .sub-categories-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 4rem;
  }
}
</style>