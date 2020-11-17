<template>
  <div>
    <div class="register-wrapper">
      <div class="copy-wrapper">
        <p class="copy">REGÍSTRESE EN NUESTRO BOLETÍN DE CORREO ELECTRÓNICO PARA LAS ÚLTIMAS NOTICIAS Y ACTUALIZACIONES DE PRODUCTOS</p>
      </div>
      <div class="register-form-wrapper">
        <div class="register-input-wrapper">
          <input type="text" name="email" placeholder="email" v-model="email">
        </div>
        <div class="register-button-wrapper">
          <button class="register-button" @click.prevent="submit">Regístrate</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        email: ''
      }
    },
    methods: {
      submit() {
        const SteinStore = require("stein-js-client");
        const store = new SteinStore(
          "https://api.steinhq.com/v1/storages/5f04cf13383a60054639522c"
        );

        store
        .append("Inelec-subscribe", [
          {
            email: this.email
          }
        ]);
      }
    }
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';

.register-wrapper {
  background: $orange;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}
.copy-wrapper {
  color: #fff;
  text-transform: uppercase;
  text-align: center;
  margin: 1rem 0;

  .copy {
    font-size: 1.8rem;
  }

}
.register-button-wrapper {
  .register-button {
    color: #fff;
    text-transform: uppercase;
     background: $dark-gray;
         font-size: 1.8rem;

  }
}

.register-form-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;

  input {
    min-width: 20rem;
    margin-right: 1rem;
    padding: 1rem;
    border: none;
        font-size: 1.8rem;

  }
}

@media screen and (min-width: 720px){
  .register-wrapper {
    flex-direction: row;
  }
  .copy-wrapper {
    text-align: left;
    margin: 0;
  }
}
</style>