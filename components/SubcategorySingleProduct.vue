<template>
  <div class="single-product-wrapper">
    <div class="image-wrapper">
      <img src="/handlamp-test.png" alt="">
    </div>
    <div class="data-wrapper">
      <div class="title-wrapper">
        <p class="title">
          WOLFLITE XT RECHARGEABLE LED HANDLAMP
        </p>
      </div>
      <div class="data-list-wrapper">
        <ul class="data-list">
          <li class="data-item">
            <strong>Models: </strong>
            XT-50, XT-70, XT-70MOD, XT-90, XT-75
          </li>
          <li class="data-item">
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
          </li>
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