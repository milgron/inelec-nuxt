<template>
  <div class="main-wrapper">
    <TitleWrapper
      :title="productName"
      backgroundColorString="orange"
      color="#202020"
    />
    <hr>
    <div class="models-wrapper">
      <p class="models">XT1, XT2, XT3</p>
    </div>
    <div class="logos-wrapper">
      <img src="/icons-product.png" alt="">
    </div>
    <div class="image-wrapper">
      <img src="/product-big.jpg" alt="">
    </div>
    <div class="copy-wrapper">
      <p class="copy">
      <strong>THE WOLFLITE XT RECHARGEABLE HANDLAMP EXPLOITS ADVANCED TECHNOLOGY TO DELIVER EXCELLENT 
      PERFORMANCE, ROBUSTNESS, RELIABILITY AND VERSATILITY IN THE HARSHEST ENVIRONMENTS AND IS CE MARKED 
      TO THE ATEX DIRECTIVE AND IECEX CERTIFIED, FOR SAFE USE IN ZONES 1 AND 2 POTENTIALLY EXPLOSIVE GAS AND 
      ZONES 21 AND 22 DUST ATMOSPHERES. A ZONE 0 AND 20 VERSION IS AVAILABLE.</strong><br><br>

      The XT Rechargeable LED Handlamp is available in a number of different models to optimise performance 
      in specific applications.  Bespoke optics and the highest performing ‘fitted for life’ LED light sources deliver 
      outstanding light output from the high intensity spot beam; ideal for tasks requiring a higher light intensity. 
      A wide-angle flood option is also available, for tasks with less extensive light requirement. Additional 
      coloured LED signals can also be added. All products of the XT range have easy, single-handed switching 
      even with gloved hands allowing for straightforward function selection.<br>

      Battery duration varies by model, from 4 hours of high output light (XT-50) to 11 hours (XT-90); selecting 
      powersave doubles this duration. State of battery charge is indicated with a bar of high intensity red LEDs, 
      which go out as battery charge diminishes and the beam flashes off repeatedly when recharging is
      required. Use of the latest lithium-ion battery technology improves reliability and eliminates ‘memory’ affect 
      and the ‘quick’ charger base fully recharges the Handlamp in a minimum of 2 hours, dependent on model, 
      and is configured as a holder with ‘snap-in/snatch-out’ function, for quick release but secure retention. 
      Emergency illumination function illuminates Handlamp if power to the charger fails.<br>

      The compact and lightweight high strength body has proven impact resistance even at sub zero 
      temperatures; enhanced by rubber armoured lens ring, and handle/sides give improved grip and shock
      protection. The lens is resistant to scratches and chemical attack; the enclosure is electrostatic 
      nonhazardous and certified to IP67.<br><br>

      Download Product Information Sheet.<br>

      IMPA Codes<br>
      33 06 12 - XT-50 Standard<br>
      33 06 13 - XT-70 Performance<br>
      33 06 14 - XT-200H<br>

      NSN Codes<br>

      6230-99-4473141  -  XT-70MOD<br>



      </p>
    </div>

    <div class="download-wrapper">
      <div class="download-icon">
        <img src="/files.png" alt="">
      </div>
      <button class="download-button">
        DESCARGAS Y RECURSOS
      </button>
    </div>
  </div>
</template>

<script>
  import TitleWrapper from '../../../../components/TitleWrapper'
  export default {
    components: {
      TitleWrapper
    },
    data() {
      return {
        productName: ''
      }
    },
    mounted() {
      const productName = this.$route.params.id
      const replacedProductName = productName.replace('-',' ')
      this.productName = replacedProductName
    }
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';

a {
  text-decoration: none;
  color: inherit;
}
.main-wrapper {
  padding: 3rem;
}

.copy-wrapper {
  margin: 1rem 0;

  .copy {
    font-size: 2.2rem;
    line-height: 1.2;
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
  background-color: $orange;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1rem;
}

.title-wrapper {
  .title{
    font-weight: bold;
    font-size: 1.8rem;
  }
}

.models-wrapper {
  margin: 1rem 0;
  .models {
    font-weight: bold;
  }
}

.logos-wrapper {
  display: flex;
  flex-direction: row;
  margin: 1rem 0;

  .logo {
    width: 30px;
    height: 30px;
    background: #000;
    &:not(:first-child) {
      margin-left: 1rem;
    }
  }
}

.download-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  background: $medium-gray;
  max-width: 28rem;
  padding: 1rem;
    font-size: 2rem;

  .download-icon {
    height: 40px;
    width: 40px;

    img {
      width: 100%;
    }
  }
  .download-button {
    border-radius: 0;
    border: none;
    margin-left: 1rem;
    color: $orange;
    font-size: 1.6rem;
    background: transparent;
    
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
    grid-gap: 2rem;
  }
}
@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 5rem 8rem;
  }
  .sub-categories-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>