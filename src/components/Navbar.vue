<script setup>

</script>

<template>
  <div class="navbar">
    <div class="logo">
      <!-- <img src="../assets/logo.png" width="100%" alt="bohemios de mexico"> -->
    </div>
    <p class="text-call">LLAME YA: 55 3477 3037</p>
    <div class="menu">
      <p><a href="#">INICIO</a></p>
      <p><a href="#">NOSOTROS</a></p>
      <p><a href="#">SERVICIOS</a></p>
      <p><a href="#">CONÓZCANOS</a></p>
      <p><a href="#">CONTACTO</a></p>
    </div>
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
  height: 200px;
  width: 200px;
  background: url('../assets/logo.png');
  background-size: contain;
  background-position: bottom;
  box-shadow: 6px 6px 8px rgba(0,0,0,0.5);
  border-radius: 0px 0px 10px 10px;
  background-color: white;
  border: none;
  background-repeat: no-repeat;
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
}

.navbar .menu p {
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

@media screen and (max-width: 1130px) {
  .navbar .menu {
    display: none;
  }
}
@media screen and (max-width: 600px) {
  .navbar .text-call {
    font-size: 18px;
  }
}
</style>
