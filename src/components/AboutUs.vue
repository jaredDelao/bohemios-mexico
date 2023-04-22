<script setup>
import { ref } from 'vue'
const dynamic = ref(1)
const text1 = ref('Nuestros excelentes servicios nos han llevado a tener participaciones importantes en medios como el radio, la televisión, e incluso en eventos particulares de personas públicas como políticos, empresarios o artistas reconocidos. <br /> Bohemios de México busca engalanar cada evento en el que somos participes, dejando un gran sabor de boca a cada persona que nos escucha.');
const text2 = ref('Somos un grupo de experimentados músicos con el mejor y más amplio repertorio; a través del tiempo, nos hemos destacado por la calidad vocal y musical que manejan todos nuestros artistas. <br> Tenemos el objetivo de fomentar en las nuevas generaciones la tradición y cultura de la música romántica y por supuesto, que todas aquellas personas que crecieron con este género, puedan revivir aquellas inolvidables melodías.');

const getColorBtn = (value) => {
  return dynamic.value === value ? '#3b2314' : '#C1B49A';
}
</script>

<template>
  <div class="about">
    <div class="logo">
      <img src="../assets/logo-max.png" alt="">
    </div>
    <div class="info">
      <div class="title">
        NOSOTROS
      </div>
      <div class="subtitle">
        Bohemios de México es una empresa que proporciona servicio artístico-musical, para todo tipo de evento.
      </div>

      <div class="dynamic">
        <Transition name="fade" mode="out-in">
          <div class="text1" v-if="dynamic === 1">
            <div v-html="text1"></div>
          </div>

          <div class="text2" v-else>
            <div v-html="text2"></div>
          </div>
        </Transition>
      </div>
      <div class="buttons">
        <button type="button" @click="dynamic = 1" @mouseenter="dynamic = 1" :style="{ backgroundColor: getColorBtn(1) }"></button>
        <button type="button" @click="dynamic = 2" @mouseenter="dynamic = 2" :style="{ backgroundColor: getColorBtn(2) }"></button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about {
  width: 100%;
  height: 100vh;
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
  padding: 0 15px;
  transition: all 0.5s ease-in-out;
  align-self: center;
}

.info .title {
  font-size: 5em;
  font-weight: 700;
  color: var(--primary);
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
  font-size: 1.5em;
  font-weight: 500;
  color: var(--primary);
  line-height: 30px;
}

.buttons {
  width: 100%;
  height: 12px;
}

.buttons button {
  border: none;
  width: 50%;
  height: 100%;
  cursor: pointer;
  transition: all 0.4s ease-in-out;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0.5;
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
  .info .dynamic {
    color: #999;
    font-size: 18px;
    min-height: auto
  }
}

</style>
