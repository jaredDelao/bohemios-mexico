<script setup>
import { ref } from 'vue';


const openMenu = ref(false)

const toggleMenu = () => {
  console.log(openMenu.value)
  openMenu.value = !openMenu.value;
}

</script>

<template>
  <div class="menu-responsive" v-show="openMenu">
    <div class="close" @click="toggleMenu">
      <img src="../assets/close.svg" alt="">
    </div>
    <ul>
      <li><a href="#">INICIO</a></li>
      <li><a href="#">NOSOTROS</a></li>
      <li><a href="#">SERVICIOS</a></li>
      <li><a href="#">CONÓZCANOS</a></li>
      <li><a href="#">CONTACTO</a></li>
    </ul>
  </div>
  <div class="navbar">
    <div class="logo">
      <img src="../assets/logo.png" width="100%" alt="bohemios de mexico">
    </div>
    <div class="menu">
      <p><a href="#">INICIO</a></p>
      <p><a href="#">NOSOTROS</a></p>
      <p><a href="#">SERVICIOS</a></p>
      <p><a href="#">ESCUCHANOS</a></p>
      <p><a href="#">VIDEO</a></p>
      <p><a href="#">GALERÍA</a></p>
      <p><a href="#">CONTACTO</a></p>
    </div>
    
    <button type="button" class="btn-menu-responsive" @click="toggleMenu"><img src="../assets/menu.svg"></button>
  </div>
</template>

<style scoped>
.navbar {
  z-index: 99;
  position: fixed;
  justify-content: space-around;
  top: 0;
  width: 100%;
  height: 90px;
  display: flex;
  box-shadow: 0px 8px 8px rgba(0, 0, 0, 0.5);
  background-color: #fffaf5b9;
  align-items: center;
}

.navbar .logo {
  width: 200px;
}

.navbar .text-call {
  font-weight: 700;
  text-shadow: 4px 4px 5px rgba(96, 56, 19, 0.5);
  font-size: 25px;
  color: var(--primary);
  margin: 0;
}

.navbar .menu {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.navbar .menu p {
  font-size: 15px;
  padding: 0px 10px;
  border-right: 3px solid var(--primary);
}

.navbar .menu p:hover {
  font-weight: 500;

}

.navbar .menu p:last-of-type {
  border-right: none;
}

.navbar .menu p a {
  text-decoration: none;
  color: var(--primary);
  transition: all 0.3s ease-in-out;
}

.navbar .menu p a:hover {
  font-weight: 700;

}

@media screen and (max-width: 920px) {
  .navbar .menu p {
    font-size: 12px;
  }
}

@media screen and (max-width: 800px) {
  .navbar .menu {
    display: none;
  }
  .navbar .btn-menu-responsive {
    display: block;
  }
}
@media screen and (max-width: 600px) {
  .navbar .text-call {
    font-size: 18px;
  }
}
@media screen and (max-width: 525px) {
  .navbar .text-call {
    display: none;
  }
}

.menu-responsive {
  width: 100%;
  height: 100vh;
  background: #222;
  color: white;
  z-index: 99999;
  position: fixed;
}

.menu-responsive .close {
  right: 10%;
  top: 10%;
  position: absolute;
  width: 50px;
  cursor: pointer;
}

.menu-responsive ul {
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  position: absolute;
  list-style: none;
}

.menu-responsive ul a {
  color: white;
  font-weight: 600;
  text-decoration: none;
  font-size: 25px;
}
.menu-responsive ul a:hover {
  text-decoration: underline;
}

.btn-menu-responsive {
  border: none;
  cursor: pointer;
  background: transparent;
  width: 50px;
  height: 50px;
  display: none;
}
</style>
