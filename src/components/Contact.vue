<template>
  <div class="container" id="contacto">
    <div class="left-column">
      <h2>
        Envíanos un correo
      </h2>
      <form action="/enviar.php" method="POST">
        <div class="form-group">
          <label for="nombre">Nombre:</label>
          <input type="text" id="nombre" name="nombre" required>
        </div>
        <div class="form-group">
          <label for="email">Correo electrónico:</label>
          <input type="text" id="email" name="email" required>
        </div>
        <div class="form-group">
          <label for="tel">Teléfono:</label>
          <input type="text" id="tel" name="tel" required>
        </div>
        <div class="form-group">
          <label for="mensaje">Escriba su mensaje:</label>
          <textarea id="mensaje" name="mensaje" rows="5" required></textarea>
        </div>
        <div class="form-group submit-btn">
          <input type="submit" value="Enviar">
        </div>
      </form>
    </div>
    <div class="right-column">
      <h2>Tels y Whatsapp</h2>
      <!-- row -->
      <div class="tels">
        <div class="tel">
          <p>Lic. Julio Cesar Castillo</p>
          <p class="tel__img"><img src="../assets/rss/wa.svg"> 55 3477 3037</p>
        </div>
        <div class="line"></div>
        <div class="tel">
          <p>Lic. Nancy Hernández</p>
          <p class="tel__img"><img src="../assets/rss/wa.svg">55 3195 0230</p>
        </div>
      </div>
      <!-- end row -->
      <h2>Aceptamos</h2>
      <div class="payments">
        <img class="img-acept md" width="100%" src="../assets/rss/pago-lg.png">
        <img class="img-acept xs" width="100%" src="../assets/rss/pago-sm.png">
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Contact',
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
  display: flex;
  justify-content: space-between;
  padding: 20px;
  background: #fff;
  color: black;
  @media screen and (max-width: 700px) {
    flex-direction: column;
  }
}

.left-column {
  width: 50%;
  padding: 20px;
  @media screen and (max-width: 700px) {
    width: 100%;
  }

  form {
    max-width: 450px;
    margin: auto;
    margin-top: 20px;
    background-color: #fff8ec;
    padding: 20px;

    .submit-btn {
      text-align: end;
      input {
        background: var(--primary);
        padding: 10px 30px;
      }
    }
  }
}

.right-column {
  padding: 20px;

  @media screen and (max-width: 700px) {
    width: 100%;
  }

  width: 50%;

  .payments {
    margin-top: 20px;
    width: 100%;
    text-align: center;

    .xs {
      display: none;
      @media screen and (max-width: 1000px) {
        display: block;
      }
    }

    .md {
      @media screen and (max-width: 1000px) {
        display: none;
      }
    }

    .img-acept {
      width: 100%;
      max-width: 500px;
      margin: auto;
    }
  }

}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
}

input[type="text"],
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

input[type="submit"] {
  padding: 10px 20px;
  background-color: #4CAF50;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

h2 {
  text-align: center;
  font-size: 2em;
  font-weight: 300;
}

.tels {
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin-top: 20px;
  margin-bottom: 30px;
  @media screen and (max-width: 550px) {
    flex-direction: column;
  }

  p {
    margin: 0;
  }

  .tel {
    padding: 10px;
    background-color: #fff8ec;

    p {
      @media screen and (max-width: 550px) {
        text-align: center;
      }
      &:first-child {
        font-size: 16px;
        font-weight: 600;
      }
    }

    &:first-child {
      border-right: 3px solid var(--secondary);
      @media screen and (max-width: 551px) {
        border-right: none;
        border-bottom: 3px solid var(--secondary);
      }
    }

    &__img {
      display: flex;
      align-items: center;
      padding: 0 10px;
      @media screen and (max-width: 550px) {
        justify-content: center;
      }

      img {
        width: 30px;
        margin-right: 3px;
      }

      &:first-of-type {
        border-right: 3px solid var(--primary);
      }
    }
  }
}

@media screen and (max-width: 700px) {

  .left-column,
  .right-column {
    width: 100%;
  }
}
</style>
