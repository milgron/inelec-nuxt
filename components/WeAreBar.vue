<template>
  <div>
    <div class="main-wrapper">
      <div class="copy-wrapper">
        <div class="copy">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illum veniam quam voluptate. Consequuntur voluptates eum facilis dolorem eos tenetur, ullam debitis molestias. Repellat nostrum maxime facilis necessitatibus laborum impedit iure.</div>
      </div>
      <div class="icons-wrapper">
        <div class="icon-wrapper">
          <img src="" alt="">
        </div>
        <div class="icon-wrapper">
          <img src="" alt="">
        </div>
        <div class="icon-wrapper">
          <img src="" alt="">
        </div>       
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
.main-wrapper {
  background: $dark-gray;
  padding: 1rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  
  .copy {
    color: #fff;
    text-transform: uppercase;
    font-size: 1.6rem;
  }
}
</style>