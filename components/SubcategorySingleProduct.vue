<template>
  <div class="single-product-wrapper">
    <div class="image-wrapper">
      <img src="/test-product.jpg" alt="">
    </div>
    <div class="data-wrapper">
      <div class="title-wrapper">
        <p class="title">
          Product name
        </p>
      </div>
      <div class="data-list-wrapper">
        <ul class="data-list">
          <li class="data-item">
            <strong>Data: </strong>
            Lorem ipsum dolor sit.
          </li>
          <li class="data-item">
            <strong>Data: </strong>
            Lorem ipsum dolor sit.
          </li>
          <li class="data-item">
            <strong>Data: </strong>
            Lorem ipsum dolor sit.
          </li>
          <li class="data-item">
            <strong>Data: </strong>
            Lorem ipsum dolor sit.
          </li>
          <li class="data-item">
            <strong>Data: </strong>
            Lorem ipsum dolor sit.
          </li>
        </ul>
      </div>
      <div class="logos-wrapper">
        <div class="logo"></div>
        <div class="logo"></div>
        <div class="logo"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    
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
}

.data-wrapper {
  flex: 1 1;
  padding: 1rem;
  background-color: $light-gray;
}

.title-wrapper {
  .title{
    font-weight: bold;
    font-size: 1.8rem;
  }
}

.data-list-wrapper {
  margin-top: 1rem;
  
  .data-list {
    .data-item {
  text-transform: none;
      font-size: 1.4rem;
    }
  }
}

.logos-wrapper {
  display: flex;
  flex-direction: row;
  margin-top: 1rem;
  .logo {
    width: 30px;
    height: 30px;
    background: #000;
    
    &:not(:first-child) {
      margin-left: 1rem;
    }
  }
}

@media screen and (min-width: 920px) {
  .single-product-wrapper {
    flex-direction: row;
  }
}

</style>