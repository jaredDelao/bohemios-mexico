<script setup>
import { ref } from 'vue'

const getColorBtn = (value) => {
  return dynamic.value === value ? '#3b2314' : '#C1B49A';
}
</script>

<template>
  <div class="services">
    <img src="../assets/services.jpeg" alt="">

    <div class="title">
      SERVICIOS
    </div>

    <p class="subtitle-1">Escucha a los mejores músicos de México, contratación de: </p>
    <p class="subtitle-2">TRÍOS, DUETOS, CUARTETOS, SOLISTAS</p>

    <p class="subtitle-others">OTROS SERVICIOS: </p>

    <p class="last-subtitle">•Mariachis, Grupos Versátiles, DJ’s, Imitadores, Payasos,
      Showman, Maestros de Ceremonias, Animadores,
      Catering / Buffet y mucho más...</p>

  </div>
</template>

<style scoped>
.services {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: 1fr;
  background-color: white;
  justify-content: center;
  background-size: cover;
  background-repeat: no-repeat;
  color: white;
  position: relative;
  padding: 10% 2%;
  text-align: center;
}

.services .title {
  font-size: 6em;
  font-weight: 100;
  color: #fff;
}

.services .subtitle-1 {
  font-size: 2em;
  margin-top: 30px;

}
.services .subtitle-2 {
  font-size: 2.5em;

}

.services .subtitle-others {
  font-size: 2.5em;
  margin-top: 50px;

}
.services .last-subtitle {
  font-size: 2em;
  margin-top: 20px;
}

.services img {
  filter: brightness(70%);
  object-fit: cover;
  z-index: 0;
  position: absolute;
  width: 100%;
  height: 100%;
}

.services>div {
  padding: 0 15px;
}

@media screen and (max-width: 800px) {
  .services .title {
    font-size: 2.5em !important;
  }

  .services .subtitle-1 {
    font-size: 1.5em;
    margin-top: 30px;
  
  }
  .services .subtitle-2 {
    font-size: 1.5em;
  
  }
  
  .services .subtitle-others {
    font-size: 1.5em;
    margin-top: 50px;
  
  }
  .services .last-subtitle {
    font-size: 1.3em;
    margin-top: 20px;
  }

}

@media screen and (max-width: 1050px) {
  .services .title {
    font-size: 4em;
  }
  
}
</style>
