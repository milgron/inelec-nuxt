<template>
  <div class="main-wrapper">
    <div class="head-wrapper">
      <TitleWrapper 
        title="Quiénes somos"
        backgroundColorString="orange"
        color="#202020"
      />
      <hr>
    </div>
    <div class="image-wrapper">
      <img src="/test-quienes-somos.jpg" alt="">
    </div>
    <div class="copy-wrapper">
      <p class="copy-main">
        <strong>Somos una empresa activa en el área de seguridad en áreas peligrosas desde hace décadas</strong>
      </p>
      <p class="copy">
        

Nuestro equipo esta conformado por jóvenes profesionales con una alta motivación para atender los 
requerimientos de un sector como el del Petroleo, Gas y Mineria, de alta especificación y demanda.
Representamos las mejores compañias del mundo en los rubros en que actuamos , garantizando 
calidad, servicio “post-venta, stock de productos y repuestos.

Nuestras oficinas, talleres y deposito se encuentran ubicadas en la Ciudad de Buenos Aires, donde , 
además, de lo expuesto, contamos con nuestros vehículos propios y personal altamente entrenado 
para realizar visita a yacimientos y asesoramientos “in-situ”.

Somos conscientes de ayudamos a nuestros clientes a preservar su patrimonio, al evitar accidentes 
por deflagración, además de cuidar su bien mas preciado, su capital humano , trabajando con una 
postura de Responsabilidad Social Empresaria, que incluye la ayuda a la preservación del 
Medio Ambiente.</p>
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
  padding: 3rem;
}
.image-wrapper {
  margin: 1rem 0;
  width: 100%;

  img {
    width: 100%;
  }
}
.copy-wrapper {
  margin: 1rem 0;

  .copy-main {
    font-weight: bold;
    font-size: 3.45rem;
  }
  .copy {
    margin: 1rem 0;
    font-size: 3.45rem;
    line-height: 1.2;
    text-transform: none;
  }
}

@media screen and (min-width: 920px) {
  .main-wrapper {
    padding: 3rem 6rem;
  }
}
</style>