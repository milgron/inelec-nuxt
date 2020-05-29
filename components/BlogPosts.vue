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
Don't be dazzled in smaller confined spaces - The WF-250XL is the ideal solution.</p>
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
Press realease - Wolf appointed exclusive UK distributor for RAMFAN™ - Market leader in ventilation for hazardous areas.</p>
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
David Lyon appointed sales manager for Scotland.</p>
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
    background: #fff;
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
    .copy {
      font-size: 2rem;
    }
  }
  .read-more-wrapper {
    margin-top: 1rem;

    .copy {
      font-weight: bold;
      font-size: 2rem;
    }
  }

@media screen and (min-width: 920px) {
  .news-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>