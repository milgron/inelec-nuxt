<template>
  <div>
    <div class="header-wrapper">
      <nuxt-link to="/">
        <div class="logo-wrapper"> 
          <img src="/logo-inelec.png" class="logo" alt="">
        </div>
      </nuxt-link>
      <div :class="[{'is-open': isDesktopSearchOpen},'links-and-search-wrapper', 'desktop']">
        <div :class="[{'hide': isDesktopSearchOpen},'links-wrapper']">
          <nuxt-link to="/" class="menu-link">
            Home
          </nuxt-link>
          <nuxt-link to="/quienes-somos" class="menu-link">
            Quiénes somos
          </nuxt-link>
          <nuxt-link to="/products/iluminacion-temporal" class="menu-link">
            Iluminación temporal
          </nuxt-link>
          <nuxt-link to="/products/accesorios" class="menu-link">
            Accesorios
          </nuxt-link>
          <nuxt-link to="/products/iluminacion-portatil" class="menu-link">
            Iluminación portátil
          </nuxt-link>
        </div>
        <div class="search-wrapper-desktop">
          <div class="icons-wrapper">
            <div :class="[{'active': !isDesktopSearchOpen},'search-icon']" @click.prevent="searchIconHandler">
              <font-awesome-icon :icon="['fas', 'search']" class="fa fa-2x icons-header"/>
            </div>
            <div :class="[{'active': isDesktopSearchOpen},'close-icon']" @click.prevent="closeIconHandler">
              <font-awesome-icon :icon="['fas', 'times']" class="fa fa-2x icons-header"/>
            </div>
          </div>
          <input type="text" name="" class="search-input" v-model="searchInput">
          <button class="submit-search">Buscar</button>
        </div>
      </div>
      <div class="menu-button-wrapper" @click="mobileMenuButtonHandler">
        <div :class="['mobile-icon-wrapper',{'hide': isMenuOpen}]">
          <font-awesome-icon :icon="['fas', 'bars']" :class="['fa-2x', 'icons-header']"/>
        </div>
        <div :class="['mobile-icon-wrapper',{'hide': !isMenuOpen}]">
          <font-awesome-icon :icon="['fas', 'times']" :class="['fa-2x']"/>
        </div>
      </div>
    </div>
    <div :class="['links-and-search-wrapper','mobile',{'is-open': isMenuOpen},]">
      <nuxt-link to="/quienes-somos" class="menu-link">
        Quiénes somos
      </nuxt-link>
      <nuxt-link to="/products/iluminacion-temporal" class="menu-link">
        Iluminación temporal
      </nuxt-link>
      <nuxt-link to="/products/accesorios" class="menu-link">
        Accesorios
      </nuxt-link>
      <nuxt-link to="/products/iluminacion-portatil" class="menu-link">
        Iluminación portátil
      </nuxt-link>
      <div class="search-wrapper-mobile">
        <input type="text" name="" class="search-input" v-model="searchInput">
          <button class="submit-search">Buscar</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isMenuOpen: false,
        searchInput: '',
        isDesktopSearchOpen: false,
      }
    },
    methods: {
      mobileMenuButtonHandler() {
        this.isMenuOpen = !this.isMenuOpen
      },
      searchIconHandler() {
        this.isDesktopSearchOpen = !this.isDesktopSearchOpen
      },
      closeIconHandler() {
        this.isDesktopSearchOpen = !this.isDesktopSearchOpen
      },
      submitSearch() {
        this.$router.push({path: `/busqueda/${this.searchInput}`})
      }
    }
    
  }
</script>

<style lang="scss" scoped>
  @import '~assets/css/colors';
  .header-wrapper {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    height: 10rem;
    align-items: center;
    background: $light-gray;
    position: relative;
    z-index: 2;
    padding: 3rem;
    box-shadow: 0px 1px 9px rgba(50,50,50,0.5);
    overflow: hidden;
  }
  .logo-wrapper {
    max-width: 20rem;
    .logo {
      width: 100%;
    }
  }
  .links-and-search-wrapper {
    color: $medium-gray;
    font-weight: bold;
    z-index: 1;
    letter-spacing: 1px;
    
    a {
      text-decoration: none;
      color: inherit;
    }

    .menu-link {
      font-family: 'Din-Condensed-Bold', sans-serif;
      text-transform: uppercase;
      font-size: 1.6rem;
      &:not(:first-child) {
        margin-left: 1rem;
      }
    }

    &.mobile {
      transform: translateY(-100%);
      transition: all 400ms ease-in-out;
      display: flex;
      flex-direction: column;
      padding: 1rem;
      background: #2a2a2a;
      
      > .menu-link {
        margin-left: 1rem;
        position: relative;
        color: #fff;

        &:not(:first-child) {
          margin-top: 1rem;
        }
      }

      &.is-open {
        transform: translateY(0);
        transition: all 400ms ease-in-out;
      }

      .search-wrapper-mobile {
        margin-top: 1rem;
        padding: .5rem;
        display: flex;
        flex-direction: row;
        justify-content: space-between;

        .search-input {
          width: 100%;
          border: none;
          padding: .5rem;
          border-bottom: 1px solid #2a2a2a;
        }
        .submit-search {
          padding: .5rem;
          font-size: 1rem;
          margin-left: 2rem;
          text-align: center;
          background: $orange;
          color: #fff;
          border: none;
        }
      }
    }

    &.desktop {
      display: none;
    }
  }
  .menu-button-wrapper {
    opacity: 1;
    position: relative;

    .mobile-icon-wrapper {
      transition: all 450ms ease-in-out;
      position: absolute; 
      left: -2.5rem;
      top: -1rem;
      opacity: 1;
      
      &.hide {
        transition: all 250ms ease-in-out;
        opacity: 0;  
        left: -2.5rem;
        top: -3rem;
      }    
    }
    cursor: pointer;
  }

  @media screen and (min-width: 920px){
    .menu-link {
      font-size: 1.6rem;
    }
    .links-and-search-wrapper {
      display: flex;
      align-items: center;
      flex-direction: row;
      &.mobile {
        display: none;
      }
      &.desktop {
        display: flex;
        transform: translateX(23rem);
        transition: all 400ms ease-in-out;
        
        &.is-open {
          transform: translateX(0);
          transition: all 400ms ease-in-out;
        }
      }
    }
    
    .menu-button-wrapper {
      display: none;
    }

    .search-wrapper-desktop {
      padding: .5rem;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      width: 25rem;

      .icons-wrapper {
        display: flex;
        flex-direction: column;
        margin-right: 2rem;
        padding: .5rem;
        width: 40px;
        height: 35px;
        position: relative;
        overflow: hidden;
      }

      .close-icon {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 25px;
        height: 25px;
        cursor: pointer;
        position: absolute;
        bottom: -3.5rem;
        left: .5rem;
        opacity: 0;
        transition: all 250ms ease-in-out;

        &.active {
          bottom: .5rem;
          left: .5rem;
          opacity: 1;
          transition: all 250ms ease-in-out;
        }
      }
      
      .search-icon {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 25px;
        height: 25px;
        cursor: pointer;
        position: absolute;
        bottom: -3.5rem;
        left: .5rem;
        opacity: 0;
        transition: all 250ms ease-in-out;

        &.active {
          bottom: .5rem;
          left: .5rem;
          opacity: 1;
          transition: all 250ms ease-in-out;
        }
      }

      .search-input {
        position: relative;
        background: transparent;
        width: 70%;
        padding: .5rem;
        border: none;
        border-bottom: 1px solid #000;
      }
      .submit-search {
        padding: .5rem;
        font-size: 1rem;
        text-transform: uppercase;
        text-align: center;
        background: $orange;
        color: #fff;
        margin-left: 1rem;
        border: none;
      }
    }
    .links-wrapper{
      opacity: 1;
      transition: all 500ms ease-in-out;

      &.hide {
        opacity: 0;
        transition: all 500ms ease-in-out;
      }
    }
  }
  .icons-header {
    color: $orange;
  }

  @media screen and (min-width: 1200px){
    .menu-link {
      font-size: 2.2rem !important;
    }
  }
</style>