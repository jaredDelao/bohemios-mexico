<template>
  <div class="container">
    <div class="flex">
      <div class="left-column">
        <span class="title">VISITA NUESTRAS <br> REDES SOCIALES</span>
      </div>
      <div class="right-column">
        <div class="rss">
          <a href="https://www.facebook.com/bohemiosdemexicooficial?mibextid=ZbWKwL" target="_blank"><img
              src="../assets/rss/footer/fb.svg" alt="Facebook"></a>
          <a target="_blank" href="https://instagram.com/bohemios_de_mexico?igshid=MzRlODBiNWFlZA=="><img src="../assets/rss/footer/ig.svg" alt="Instagram"></a>
          <a target="_blank" href="https://www.tiktok.com/@bohemios_de_mexico?_t=8cMxsky4k5t&_r=1"><img src="../assets/rss/footer/tiktok.svg" alt="Tiktok"></a>
          <a target="_blank" href="https://youtube.com/@bohemiosdemexico"><img src="../assets/rss/footer/yt.svg" alt="Youtube"></a>
        </div>
      </div>
    </div>
    <p class="derechos">Todos los derechos reservados para Bohemios de México 2023©</p>
    <a href="#">
      <p class="aviso-privacidad">Aviso de privacidad</p>
    </a>
  </div>
</template>

<script>

export default {
  name: 'Footer',
  components: {
  },
  data() {
    return {

    }
  },
  methods: {

  },
}
</script>

<style scoped lang="scss">
.container {
  padding: 50px 30px;
  background: var(--secondary);
  color: black;
  text-align: center;

  a {
    color: black;
  }

  .derechos {
    margin-top: 40px;
    margin-bottom: 20px;
    font-size: 18px;
    letter-spacing: 3px;
  }

  .aviso-privacidad {
    font-size: 18px;
    letter-spacing: 3px;
  }

  .flex {
    display: flex;
    flex-direction: row;
    align-items: center;

    @media screen and (max-width: 820px) {
      flex-direction: column;
    }

    .left-column {
      width: 50%;
      text-align: center;

      @media screen and (max-width: 820px) {
        width: 100%;
      }

      .title {
        font-size: 2em;
        line-height: 1.2em;
      }
    }

    .right-column {
      width: 50%;
      text-align: center;

      @media screen and (max-width: 820px) {
        width: 100%;
      }

      .rss {
        display: flex;
        flex-direction: row;

        @media screen and (max-width: 820px) {
          justify-content: center;
          margin-top: 30px;
        }

        img {
          width: 70px;
          margin: 0 10px;

          @media screen and (max-width: 500px) {
            width: 50px;
          }
        }
      }
    }
  }
}</style>
