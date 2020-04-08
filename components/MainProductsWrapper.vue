<template>
  <div>
    <div class="main-products-wrapper">
      <div class="product-wrapper primary">
        <div class="image-wrapper">
          <p>imagen</p>
        </div>
        <div class="data-wrapper">
          <div class="title-wrapper">
            <h2 class="title"><span class="wrapper">asdasdasd</span></h2>
          </div>
          <div class="subtitle-wrapper">
            <p class="subtitle"><span class="wrapper">Lorem ipsum dolor sit amet.</span></p>
          </div>
          <div class="copy-wrapper">
            <div class="copy">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur dolore quam ex, repudiandae eligendi suscipit architecto vel id cum expedita unde magni, nesciunt dolor porro, beatae facilis! Quis, fugit quam!
            </div>
          </div>
        </div>
      </div>
      <div class="products-wrapper secondary">
        <div class="product-wrapper secondary-top">
          <div class="image-wrapper">
            <p>imagen</p>
          </div>
          <div class="data-wrapper">
            <div class="new-wrapper">
              <p class="copy"><span class="wrapper">New</span></p>
            </div>
            <div class="title-wrapper">
              <h2 class="title"><span class="wrapper">asdasdasd</span></h2>
            </div>
            <div class="copy-wrapper">
              <div class="copy">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur dolore quam ex, repudiandae eligendi suscipit architecto vel id cum expedita unde magni, nesciunt dolor porro, beatae facilis! Quis, fugit quam!
              </div>
            </div>
          </div>
        </div>
        <div class="product-wrapper secondary-bottom">
          <div class="image-wrapper">
            <p>imagen</p>
          </div>
          <div class="data-wrapper">
            <div class="new-wrapper">
              <p class="copy"><span class="wrapper">New</span></p>
            </div>
            <div class="title-wrapper">
              <h2 class="title"><span class="wrapper">asdasdasd</span></h2>
            </div>
            <div class="copy-wrapper">
              <div class="copy">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur dolore quam ex, repudiandae eligendi suscipit architecto vel id cum expedita unde magni, nesciunt dolor porro, beatae facilis! Quis, fugit quam!
              </div>
            </div>
          </div>
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
  
  .main-products-wrapper {
    display: flex;
    flex-direction: column;
  }
  .product-wrapper {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    border: 1px solid blue;

    &.primary {
      background: $medium-gray;
      
      .title-wrapper {
        .title {
          color: $dark-gray;
        }
        .wrapper {
          background: $orange;          
        }
      }

      .subtitle-wrapper {
        margin-top: 1.5rem;
        
        .wrapper {
          background: $light-gray;
        }
      }

      .wrapper {
        padding: .5rem;
      }

      .copy-wrapper {
        margin-top: 1.5rem;

        .copy {
          color: #fff;
        }
      }

    }
    &.secondary-top {
      background: $orange;
    }
    &.secondary-bottom {
      background: $dark-gray;
      color: $light-gray;
    }
  }

  .secondary-top,.secondary-bottom {
    .data-wrapper {
      .title {
        margin: 1rem 0;
      }
    }
  }

  .data-wrapper {
    text-transform: uppercase;
    .copy {
      .wrapper {
        margin-bottom: 2rem;
        padding: .5rem; 
        background: $light-gray;
      }
    }
  }

  .image-wrapper {
    margin-bottom: 2rem;
  }

  .new-wrapper {
    .copy {
      color: $dark-gray;
    }
  }

  @media screen and (min-width: 920px) {
    .main-products-wrapper {
      display: flex;
      flex-direction: row;
    }
    .products-wrapper {
      width: 50%;
    }

    .image-wrapper {
      margin-bottom: 0;
      width: 40%;
      border: 1px solid red;
    }

    .data-wrapper {
      width: 60%;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .product-wrapper {
      display: flex;
      flex-direction: row-reverse;
      align-items: center;

      &.primary {
        width: 50%;
      }
    }
  }
</style>