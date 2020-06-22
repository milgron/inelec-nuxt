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
              <input type="text" name="name" id="">
            </div>
            <div class="form-row-wrapper email-phone">
              <div class="email-input-wrapper">
                <label for="email">Email*</label>
                <input type="text" name="email" id="">
              </div>
              <div class="phone-input-wrapper">
                <label for="phone">Teléfono*</label>
                <input type="text" name="phone" id="">
              </div>
            </div>
            <div class="form-row-wrapper">
              <label for="company">Empresa*</label>
              <input type="text" name="company" id="">
            </div>
            <div class="form-row-wrapper">
              <label for="message">Mensaje*</label>
              <textarea name="message" cols="30" rows="10"></textarea>
            </div>
            <div class="submit-button-wrapper mobile">
              <button class="submit">Enviar</button>
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
          <div style="width: 100%; margin-top: 1rem; border: 1px solid #ddd; display: flex; flex-direction: column; justify-content: flex-end;"><iframe width="100%" height="200" src="https://maps.google.com/maps?width=100%&height=600&hl=es&q=Correa%203039%20Buenos%20Aires+(Inelec)&ie=UTF8&t=&z=15&iwloc=B&output=embed" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"><a href="https://www.mapsdirections.info/calcular-ruta.html">Calcular Ruta</a></iframe></div>
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
          <button class="submit">Enviar</button>
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
  export default {
    components: {
      RegisterBar
    }
  }
</script>

<style lang="scss" scoped>
@import '~assets/css/colors';

.columns-wrapper {
  max-width: 1024px;
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
}

.form-wrapper, .contact-data-wrapper {
  margin: 1rem 0;
}

.form-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
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

  input {
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
  
}
</style>