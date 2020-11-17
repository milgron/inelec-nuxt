<template>
  <div>
    <div class="main-wrapper">
      <RegisterBar />
      <div class="form-and-data-wrapper">
        <div class="form-wrapper">
          <div class="title-wrapper">
            <p class="">¿Querés un presupuesto personalizado?</p>
          </div>
          <div class="form-group">
            <div class="form-row-wrapper">
              <label for="name">Nombre*</label>
              <input type="text" name="name" id="" v-model="name">
            </div>
            <div class="form-row-wrapper email-phone">
              <div class="email-input-wrapper">
                <label for="email">Email*</label>
                <input type="text" name="email" id="" v-model="email">
              </div>
              <div class="phone-input-wrapper">
                <label for="phone">Teléfono*</label>
                <input type="text" name="phone" id="" v-model="phone">
              </div>
            </div>
            <div class="form-row-wrapper">
              <label for="company">Empresa*</label>
              <input type="text" name="company" id="" v-model="company">
            </div>
            <div class="form-row-wrapper">
              <label for="message">Mensaje*</label>
              <textarea name="message" cols="30" rows="10" v-model="message"></textarea>
            </div>
            <div class="submit-button-wrapper mobile">
              <button class="submit" @click.prevent="submit">Enviar</button>
              <div v-show="sended" class="alert-wrapper">
                <p class="alert-submit">El mensaje ha sido enviado</p>
              </div>
              <div v-show="enviando" class="alert-wrapper">
                <p class="alert-submit">El mensaje está siendo enviado</p>
              </div>
            </div>
          </div>
        </div>
        <div class="contact-data-wrapper">
          <div class="data-content">
            <div class="icon">
              <img src="/geo.png" alt="">
            </div>
            <p class="footer-direccion">
            Dirección:<br>
            Correa 3039 (CP 1429)<br>
            CABA, Argentina.
            </p> 
          </div>
          <div class="map-wrapper">
            <img src="/mapa_inelec.jpg" alt="mapa-inelec">
            <div class="link-button-wrapper">
              <a href="https://maps.google.com/maps?ll=-34.545968,-58.478877&z=15&t=m&hl=es&gl=US&mapclient=embed&q=Correa%203039%20Buenos%20Aires" target="_blank">Ver Google Maps</a>
            </div>
          </div>
        </div>
        <div class="contact-data-wrapper">
          <div class="data-content">
            <p class="title">Contacto</p>
            <div class="data-row">
              <div class="icon">
                <img src="/phone.png" alt="">
              </div>
              <p class="copy">+54 (011) 5272 5252</p>
            </div>
            <div class="data-row">
              <div class="icon">
                <img src="/mail.png" alt="">
              </div>
              <p class="copy">info@inelecsafety.com</p>
            </div>
          </div>
          <div class="data-row logo-wrapper">
            <img src="/logo-footer.png" alt="" class="logo">
          </div>
        </div>
      </div>
      <div class="submit-wrapper desktop">
        <div class="submit-button-wrapper">
          <button class="submit"  @click.prevent="submit">Enviar</button>
        </div>
        <div v-show="sended"  class="alert-wrapper">
          <p class="alert-submit">El mensaje ha sido enviado</p>
        </div>
        <div v-show="enviando" class="alert-wrapper">
          <p class="alert-submit">El mensaje está siendo enviado</p>
        </div>
      </div>
      <div class="logos-wrapper">
        <img src="/footer-icons.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
  import RegisterBar from '../components/RegisterBar'
  import axios from 'axios'
  export default {
    components: {
      RegisterBar
    },
    data() {
      return {
        name: '',
        email: '',
        phone: '',
        company: '',
        message: '',
        sended: false,
        enviando: false
      }
    },
    methods: {
      async submit() {
        this.enviando = true;
        await axios.post('https://thepipeline.xyz/api/mailer', {
          name: this.name,
          email: this.email,
          phone: this.phone,
          company: this.company,
          message: this.message,
          usr_code: "352AAt$axx__"
        }).then(res => res.json())
        .catch(error => console.error('Error:', error))
        .then(response => {
          this.enviando = false;
          this.sended = true;
        });
      }
    }
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';
.columns-wrapper {
  max-width: 100%;
  padding: 2rem;
  margin: auto;
}

.icon {
  width: 52px;
  height: 52px;
  margin-bottom: 1rem;

  img {
    width: 100%;
  }
}

.logos-wrapper {
  background: $medium-gray;
  padding: 1rem;
  color: #fff;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.data-row {
  margin: 1rem 0;
  display: flex;
  flex-direction: row;
  align-items: center;

  .copy {
    max-width: 80%;
  }

  .icon {
    margin-right: 1rem;
  }

  .logo {
    width: 100%;
    max-width: 30rem;
    margin-bottom: 5rem;
  }
}
.form-and-data-wrapper {
  background: $medium-gray;
  color: #fff;
  padding: 5rem 5rem 1rem 5rem;
  display: grid;
  grid-template-columns: 1fr;
  width: 100%;
}

.form-wrapper, .contact-data-wrapper {
  margin: 1rem 0;
}

.form-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  max-width: 80%;
}

.contact-data-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.title {
  font-size: 1.6rem;
  font-weight: bold;
  line-height: 2;
}

.form-row-wrapper {
  display: flex;
  flex-direction: column;
  margin: 1rem 0 0;

  input,textarea {
    color: #000;
  }

  &.email-phone {
    flex-direction: row;
    justify-content: space-between;

    .phone-input-wrapper,
    .email-input-wrapper {
      display: flex;
      flex-direction: column;
    }
  }

  label {
    font-size: 1.4rem;
    margin-bottom: .5rem;
  }
  input {
    padding: 1rem;
    font-size: 1.4rem;
  }
}

.submit-button-wrapper {
  background: $medium-gray;
  margin-top: 1rem;

  .submit {
    background: $dark-gray;
    color: #fff;
    padding: 1rem;
    font-size: 1.4rem;
    border-radius: 0;
    border: none;
  }
}

.submit-wrapper.desktop{
  display: none;
}

.map-wrapper {
  position: relative; 
  img {
    width: 100%;
  }
}

.link-button-wrapper {
  position: absolute; 
  bottom: 10px;
  left: 0;
  right: 0;
  margin: auto;
  max-width: 150px;
  background: #fff;
  padding: 1rem;
  display: flex;
  flex-direction: row;
  justify-content: center;
  box-shadow: 3px 3px 3px rgba($color: #000000, $alpha: 0.5);

  a {
    text-decoration: none;
    color: #000;
    text-align: center;
    font-size: 1.4rem;
  }

}

@media screen and (min-width: 920px) {
  .form-and-data-wrapper {
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 3rem;
    justify-content: center;
  }  
  .submit-wrapper.desktop {
    display: flex;
    background: $medium-gray;
  }

  .submit-button-wrapper {
    margin-top: 0;
    padding-left: 5rem;

    &.mobile {
      display: none;
    }
  }
  .data-content {
  .data-row {
    margin: 2rem 0;
      .copy {
        font-size: 2rem;
      }
  }
}

.alert-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding-left: 1rem;
}

.alert-submit {
  color: #fff;
}
  
}
</style>