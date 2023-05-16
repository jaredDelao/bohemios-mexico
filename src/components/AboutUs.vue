<script setup>
import { ref } from 'vue'

const getColorBtn = (value) => {
  return dynamic.value === value ? '#3b2314' : '#C1B49A';
}
</script>

<template>
  <div class="about">
    <div class="info">
      <div class="title">
        NOSOTROS:
      </div>
      <div class="subtitle">
        <p>Somos un grupo de músicos destacados con
          gran experiencia y un gran repertorio, en el
          ámbito del bolero, el romanticismo, la
          balada y otros géneros.</p>

        <p>Nos respaldan más de 50 años, heredando el
          talento y convicción de nuestros abuelos.</p>

        <p>
          Buscamos engalanar tu evento, brindando
          una excelente interpretación musical y una
          experiencia inigualable.
        </p>
      </div>
    </div>
    <div class="logo">
      <img src="../assets/logo-max.png" alt="">
    </div>
  </div>
</template>

<style scoped>
.about {
  width: 100%;
  height: 100%;
  padding: 80px 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  background-color: white;
  place-content: center;
}

.logo {
  align-self: center;
  text-align: center;

}

.logo img {
  width: 90%;
}

.info {
  padding: 0 30px;
  transition: all 0.5s ease-in-out;
  align-self: center;
}

.info .title {
  font-size: 5em;
  font-weight: 700;
  color: var(--primary);
}

.info .subtitle {
  font-size: 1.5em;
  font-weight: 300;
  color: var(--primary);
  line-height: 1.4em;
}

.info .subtitle p {
  margin-bottom: 20px;
}

.buttons {
  width: 100%;
  height: 12px;
}


@media screen and (max-width: 800px) {
  .info .title {
    font-size: 3em;
  }

  .about {
    grid-template-columns: 1fr;
    grid-template-rows: auto 1fr;
  }

  .logo img {
    width: 60%;
  }
}

@media screen and (max-width: 500px) {
  .info .subtitle {
    font-size: 20px;
  }
}
</style>
