<script setup>
import { ref } from 'vue'

const getColorBtn = (value) => {
  return dynamic.value === value ? '#3b2314' : '#C1B49A';
}
</script>

<template>
  <div class="services">
    <img src="../assets/services.jpeg" alt="">
    <div class="info">
      <div class="title">
        SERVICIOS
        <br>
      </div>
      <div class="subtitle">El mejor y más Amplio Repertorio:</div>
      <br>
      <div class="service-line">
        - TRÍOS
        <br>
        - DUETOS
        <br>
        - CUARTETOS
        <br>
        - SOLISTAS
      </div>
    </div>
    <div class="info2">
      <p>CONTAMOS CON TODO AQUELLO QUE AYUDE AL ENTRETENIMIENTO DE SUS EVENTOS SOCIALES Y/O EMPRESARIALES:</p>
      <ul>
        <li>Mariachis</li>
        <li>Grupos Versátiles</li>
        <li>Imitadores</li>
        <li>Payasos</li>
        <li>Showman</li>
        <li>Maestros de Ceremonias</li>
        <li>Animadores</li>
      </ul>
    </div>

    <p class="end-text">PREGUNTE POR TODOS LOS SERVICIOS <br /> COMPLEMENTARIOS QUE PODEMOS OFRECERLE</p>
  </div>
</template>

<style scoped>
.services {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  background-color: white;
  justify-content: center;
  background-size: cover;
  background-repeat: no-repeat;
  color: white;
  position: relative;
  padding: 10% 2%;
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

.info {
  transition: all 0.5s ease-in-out;
}

.info .service-line {
  font-size: 35px;
}

.info .title {
  font-size: 6em;
  font-weight: 700;
  line-height: 80px;
}

.info .dynamic {
  margin-top: 20px;
  margin-bottom: 20px;
  transition: all 0.5s ease-in-out;

}

.info .dynamic {
  color: #999;
  font-size: 18px;
  min-height: 231px;
}

.info .subtitle {
  margin-top: 10px;
  font-size: 1.5em;
  font-weight: 500;
}

.info2 p {
  font-weight: 300;
  font-size: 22px;
}

.info2 ul {
  font-size: 30px;
}

.end-text {
  width: 100%;
  text-align: center;
  grid-column-start: 1;
  grid-column-end: 3;
  font-size: 25px;
  font-weight: 300;
  margin-top: 5%;
}

@media screen and (max-width: 1050px) {
  .info .title {
    font-size: 4em;
  }
}

@media screen and (max-width: 800px) {

  .services {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr auto auto;
  }

  .services .info {
    font-size: 20px;
  }

  .info .subtitle,
  .info .service-line {
    font-size: 20px;
  }

  .services .info2 {
    font-size: 20px;
  }
  .info2 p, .info2 ul {
    font-size: 20px;
  }

  .services .info .title {
    font-size: 2.5em;
    text-align: center;
  }

  .end-text {
    font-size: 20px;
    grid-column-end: 2;
  }

  .logo img {
    width: 60%;
  }

  .info .dynamic {
    color: #999;
    font-size: 18px;
    min-height: auto
  }
}
</style>
