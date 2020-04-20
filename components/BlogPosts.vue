<template>
  <div class="main-wrapper">
    <div class="header-wrapper">
      <TitleWrapper 
        title="Novedades - Blog"
        color="#FFF"
        background="dark-gray"
      />
    </div>
    <div class="news-wrapper">
      <div class="post-wrapper">
        <div class="image-wrapper">
          <img src="/test-quienes-somos.jpg" alt="">
        </div>
        <TitleWrapper 
          title="04/12/1991"
          color="#EF7C00"
          background="dark-gray"
        />
        <div class="excerpt-wrapper">
          <p class="copy">
DON’T BE DAZZLED IN SMALLER CONFINED 
SPACES - THE WF-250XL IS THE IDEAL 
SOLUTION          </p>
        </div>
        <div class="read-more-wrapper">
          <div class="copy">Read more</div>
        </div>
      </div>
      <div class="post-wrapper">
        <div class="image-wrapper">
          <img src="/test-quienes-somos.jpg" alt="">
        </div>
        <TitleWrapper 
          title="04/12/1991"
          color="#EF7C00"
          background="dark-gray"
        />
        <div class="excerpt-wrapper">
          <p class="copy">
PRESS RELEASE - WOLF APPOINTED EXCLUSIVE UK 
DISTRIBUTOR FOR RAMFAN™ - MARKET LEADER IN 
VENTILATION FOR HAZARDOUS AREAS READ MORE          </p>
        </div>
        <div class="read-more-wrapper">
          <div class="copy">Read more</div>
        </div>
      </div>
      <div class="post-wrapper">
        <div class="image-wrapper">
          <img src="/test-quienes-somos.jpg" alt="">
        </div>
        <TitleWrapper 
          title="04/12/1991"
          color="#EF7C00"
          background="dark-gray"
        />
        <div class="excerpt-wrapper">
          <p class="copy">
DAVID LYON APPOINTED SALES MANAGER FOR 
SCOTLAND          </p>
        </div>
        <div class="read-more-wrapper">
          <div class="copy">Read more</div>
        </div>
      </div>
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
    padding: 5rem;
  }
  .header-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }
  .news-wrapper {
    margin: 1rem 0;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 3rem;
  }
  .image-wrapper {
    margin-bottom: 3rem;

    img {
      width: 100%;
    }
  }
  .excerpt-wrapper {
    text-transform: uppercase;

    .copy {
      font-size: 2rem;
    }
  }
  .read-more-wrapper {
    margin-top: 1rem;

    .copy {
      font-weight: bold;
      text-transform: uppercase;
      font-size: 2rem;
    }
  }

@media screen and (min-width: 920px) {
  .news-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>