<template>
  <div class="main-wrapper">
    <div class="head-wrapper">
      <TitleWrapper 
        title="Quiénes somos"
        backgroundColorString="#EF7C00"
        color="#202020"
      />
      <hr>
    </div>
    <div class="image-wrapper">
      <img src="/test-quienes-somos.jpg" alt="">
    </div>
    <div class="copy-wrapper">
      <p class="copy-main">
        <strong>Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, commodi!</strong>
      </p>
      <p class="copy">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Temporibus aliquam similique cum ratione, doloremque esse dicta error ipsum aspernatur, unde iste exercitationem nihil vel vero assumenda quia delectus ea ipsam!
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Temporibus aliquam similique cum ratione, doloremque esse dicta error ipsum aspernatur, unde iste exercitationem nihil vel vero assumenda quia delectus ea ipsam!
      </p>
      <p class="copy">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Temporibus aliquam similique cum ratione, doloremque esse dicta error ipsum aspernatur, unde iste exercitationem nihil vel vero assumenda quia delectus ea ipsam!
      </p>
      <p class="copy">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Temporibus aliquam similique cum ratione, doloremque esse dicta error ipsum aspernatur, unde iste exercitationem nihil vel vero assumenda quia delectus ea ipsam!
      </p>
      <p class="copy">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Temporibus aliquam similique cum ratione, doloremque esse dicta error ipsum aspernatur, unde iste exercitationem nihil vel vero assumenda quia delectus ea ipsam!
      </p>
    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../components/TitleWrapper'
  export default {
    components: {
      TitleWrapper
    }
  }
</script>

<style lang="scss" scoped>
.main-wrapper {
  padding: 3rem;
}
.image-wrapper {
  margin: 1rem 0;
  width: 100%;

  img {
    width: 100%;
  }
}
.copy-wrapper {
  margin: 1rem 0;

  .copy-main {
    font-weight: bold;
    font-size: 1.8rem;
  }
  .copy {
    margin: 1rem 0;
    font-size: 1.8rem;
    line-height: 1;
    text-transform: none;
  }
}

@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 3rem 6rem;
  }
}
</style>