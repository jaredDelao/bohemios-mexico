<script setup>
import Player from './player.vue'
</script>

<template>
  <div class="meetUs">
    <div class="title">
      <h4>CONÓZCANOS</h4>
    </div>
    <div class="info">
      <p>Lo invitamos a escuchar una de nuestras canciones:</p>
      <br>
      <div class="video">
        <p>A primera vista</p>
        <Player song="primera" name="A primera vista" />
      </div>
      <br>
      <div class="video">
        <p>Costumbres</p>
        <Player song="costumbres" name="Costumbres" />
      </div>
      <br>
      <div class="video">
        <p>No</p>
        <Player song="no" name="No" />
      </div>
    </div>
    <div class="info2">
      <p class="text-visit">Visítenos en nuestras Redes Sociales</p>

      <div class="rss">
        <div class="yt">
          <a href="">
            <img src="../assets/rss/yt.svg" alt="">
            <p>YouTube</p>
          </a>
        </div>
        <div class="fb">
          <a href="">
            <img src="../assets/rss/fb.svg" alt="">
            <p>Facebook</p>
          </a>
        </div>
      </div>
      <p class="service-text">EL MEJOR SERVICIO, PARA EL MEJOR EVENTO.</p>
    </div>

  </div>
</template>

<style scoped lang="scss">
.meetUs {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  background-color: black;
  justify-content: center;
  background-size: cover;
  background-repeat: no-repeat;
  color: white;
  position: relative;
  padding: 10% 2%;
}

.meetUs .title {
  text-align: center;
  grid-column-start: 1;
  grid-column-end: 3;
  font-size: 6em;
  font-weight: 700;
  margin-bottom: 30px;
}

.meetUs>div {
  padding: 0 15px;
}

.video > p {
  margin-bottom: 5px;
  font-size: 18px;
}

.info {
  p:first-of-type {
    font-size: 20px;
  }
}

.info2 {
  .text-visit {
    text-align: center;
    font-size: 20px;
  }
  .rss {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    margin-bottom: 20px;
    align-items: baseline;
    img {
      opacity: 0.8;
      &:hover {
        opacity: 1;
      }
    }
    a {
      text-decoration: none;
      color: white;
    }
  }
  .service-text {
    font-size: 18px;
    font-weight: 300;
    text-align: center;
  }
}




@media screen and (max-width: 800px) {

  .meetUs {
    grid-template-columns: 1fr;
  }

  .meetUs .title {
    font-size: 2.5em;
  }
  .meetUs {
    .info {
      grid-column-start: 1;
      grid-column-end: 1;
    }
    .info2 {
      grid-column-start: 1;
      grid-column-end: 1;
    }
  }
  
  .info2 {
    margin-top: 30px;
    .rss {
      justify-content: center;
      & > div {
        margin: 0 20px;
      }
    }
  }
}
</style>
