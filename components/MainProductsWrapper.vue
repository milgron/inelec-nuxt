<template>
  <div>
    <div class="main-products-wrapper">
      <div class="product-wrapper primary">
        <div class="image-wrapper">
          <img src="/main-product-1.png" alt="">
        </div>
        <div class="data-wrapper">
          <div class="title-wrapper">
            <h2 class="title"><span class="wrapper">NEW - LINKER
WF-250XL LED FLOODLITE</span></h2>
          </div>
          <div class="subtitle-wrapper">
            <p class="subtitle"><span class="wrapper">DELIVERS THE optimum light level when working on confined spaces</span></p>
          </div>
          <div class="copy-wrapper">
            <div class="copy">
              linkable sockets and low power consumption - ideal for multiple light configurations. robust, compact and lightweight - easy portable.
            </div>
          </div>
        </div>
      </div>
      <div class="products-wrapper secondary">
        <div class="product-wrapper secondary-top">
          <div class="image-wrapper">
            <img src="/main-product-2.png" alt="">
          </div>
          <div class="data-wrapper">
            <div class="new-wrapper">
              <p class="copy"><span class="wrapper">New</span></p>
            </div>
            <div class="title-wrapper">
              <h2 class="title"><span class="wrapper">NEW PORTABLE ATEX
VENTILATION</span></h2>
            </div>
            <div class="copy-wrapper">
              <div class="copy">
EXCLUSIVE UK DISTRIBUTORS OF RAMFAM
EX VENTILATION UNITS              </div>
            </div>
          </div>
        </div>
        <div class="product-wrapper secondary-bottom">
          <div class="image-wrapper">
            <img src="/main-product-3.png" alt="">
          </div>
          <div class="data-wrapper">
            <div class="new-wrapper">
              <p class="copy"><span class="wrapper">New</span></p>
            </div>
            <div class="title-wrapper">
              <h2 class="title"><span class="wrapper">EMERGENCY LUMINAIRE
LX-400E</span></h2>
            </div>
            <div class="copy-wrapper">
              <div class="copy">
WITH EMERGENCY BATTERY BACKUP AND
SOVI TECHNOLOGY!
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
    padding: 3rem;

    .title-wrapper {
      .title {
        font-size: 4rem;
      }
    }
    .subtitle-wrapper {
      .wrapper {
        line-height: 1.9;
      }
      .subtitle {
        font-size: 1.8rem;
      }
    }
    .copy-wrapper {
      .copy {
        font-size: 1.8rem;
      }
    }
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
    padding: .5rem;
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
    max-width: 20rem;

    img {
      width: 100%;
    }
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