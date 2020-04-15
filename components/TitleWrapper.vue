<template>
  <div>
    <div class="title-wrapper">
      <div class="copy">
        <span class="wrapper" :style="[{'color': color, 'background-color': backgroundColor}]">
          {{title}}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      title: String,
      color: String,
      backgroundColorString: String
    },
    data() {
      return {
        backgroundColor: ''
      }
    },
    mounted() {
      switch (this.backgroundColorString) {
        case 'dark-gray':
          this.backgroundColor = '#202020';
          break;
        case 'medium-gray':
          this.backgroundColor = '#3D3D3B';
          break;
        case 'light-gray':
          this.backgroundColor = '#EFEFEF';
          break;
        case 'orange':
          this.backgroundColor = '#EF7C00';
          break;
      
        default:
          this.backgroundColor = '#000';
          break;
      }
    }
  }
</script>

<style lang="scss" scoped>
.title-wrapper {
  margin: 1.5rem 0;
  .copy {
    .wrapper {
      font-size: 2.5rem;
      text-transform: uppercase;
      padding: 1rem;
      line-height: 1.8;
      font-weight: bold;
    }
  }
}
</style>