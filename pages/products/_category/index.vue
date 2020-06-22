<template>
  <div class="main-wrapper">
    <TitleWrapper :title="category" backgroundColorString="orange" color="#202020" />
    <hr />
    <div class="copy-wrapper">
      <p class="copy">{{categoryCopy}}</p>
    </div>
    <div class="sub-categories-wrapper">
      <nuxt-link
        :to="`/products/${category}/${childCategory.id}`"
        v-for="childCategory in childCategories"
        :key="childCategory.id"
      >
        <div class="single-sub-category-wrapper">
          <div class="image-wrapper">
            <img :src="childCategory.image_url ? childCategory.image_url : '/main-product-2.png'" alt />
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
      childCategories: [],
      categoryCopy: ''
    };
  },
  mounted() {
    const category = this.$route.params.category;
    const replacedCategory = category.replace("-", " ");
    this.category = replacedCategory;
    switch (category) {
      case "iluminacion-portatil":
        this.categoryCopy = "Wolf safety ofrece la gama más amplia de iluminación de área peligrosa certificada atex e iecex para uso seguro en atmósferas potencialmente explosivas en todo el mundo.la gama incluye linternas de mano a prueba de explosión, faros y mangueras, incluyendo la renovada manillar wolflite, con versión de bombilla y led para uso con células primarias o baterías y cargadores recargables."
        break;
      case "iluminacion-temporal":
        this.categoryCopy = "Wolf safety ofrece la gama más amplia de iluminación de área peligrosa temporal certificada atex e iecex para un uso seguro en atmósferas potencialmente explosivas en todo el mundo. la gama incluye redes protegidas de explosión y luminarias temporales fluorescentes y led de bajo voltaje y luces de inundación, kits de iluminación de tanque, lámparas de mano, luces de trabajo led operadas con batería y lámparas neumáticas operadas con aire comprimido."
        break;
    
      default:
        break;
    }
  },
  async fetch() {
    let categories = await this.$http.$get(
      "https://inelecdata.vidasremotas.xyz/wp-json/wp/v2/categories?per_page=100"
    );
    let filteredCategories = categories.map(category => {
      return {
        id: category.id,
        category: category.name,
        parent: category.parent,
        image_url: category.acf.image ? category.acf.image.url : false
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
  background: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2rem;
  height: 400px;
  transition: all 400ms ease-in-out;

  &:hover {
    transition: all 400ms ease-in-out;
    box-shadow: 3px 3px 3px rgba(100,100,100,0.75);
    font-size:4rem;
  }
}

.title-wrapper {
  margin-top: 2rem;
  .title {
    font-weight: bold;
    font-size: 3rem;
    text-align: center;
    text-transform: none;
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