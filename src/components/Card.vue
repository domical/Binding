<template>
    <form>
      <div>
        <label>Título de la tarjeta: </label>
        <input v-model="titulo" type="text" placeholder="Ejemplo Visa Classic Crédito">
      </div>

      <div>
        <label>Chip SRC: </label>
        <input v-model="chipSrc" type="text" placeholder="Ingresa ../assets/chip.png"/>
      </div>

      <div>
        <label>Número: </label>
        <input v-model="numero" type="tel" placeholder="400 500 600 700"/>
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExpiracion" type="month"/>
      </div>

      <div>
        <label>Propietario: </label>
        <input v-model="propietario" type="text" placeholder="William Henry Gates III"/>
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input v-model="tarjetaSrc" type="text" placeholder="Ingresa ../assets/visa.png"/>
      </div>
    </form>

    <div class="carnet">
      <h3>{{titulo}}</h3>
      <img :src="chipSrc" width="40"  alt="Chip" />
      <div>
        <h2>{{ numero }}</h2>
        <span>Fecha Exp: <b>{{ fechaExpiracion }}</b></span>
      </div>
      <footer>
        <span>{{ propietario }}</span>
        <img :src="tarjetaSrc" width="60" alt="Visa"/>
      </footer>
    </div>
</template>

<script>

import tarjetaImg from '../assets/visa.png';
import chipImg from '../assets/chip.png';

export default {
  name: 'Card',
  data() {
      return {
          titulo: '',
          chipSrc: chipImg,
          numero: '',
          fechaExpiracion: '',
          propietario: '',
          tarjetaSrc: tarjetaImg,
      };
  }
};
</script>

<style scoped>
  * {
      margin: 0;
    }
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 60vh;
      font-size: 10px;
      font-family: sans-serif;
    }

    #app {
      display: flex;
      gap: 40px;
    }
    form {
      padding: 18px;
      border-radius: 20px;
      border: ridge 1px;
      box-shadow: 1px 1px 1px 1px gray;
      font-weight: bold;
      display: flex;
      flex-direction: column;
      gap: 15px;
      justify-content: center;
    }
    form div {
      display: grid;
      grid-template-columns: 100px 200px;
      align-items: center;
      gap: 5px;
    }

    form div label {
      text-align: right;
    }

    .carnet {
      width: 400px;
      height: 230px;
      background: #1c1a1e;
      color: white;
      border-radius: 20px;
      padding: 20px;
      box-shadow: 0px 0px 10px 2px black;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    h3 {
      font-size: 20px;
    }

    h2 {
      font-size: 30px;
      letter-spacing: 10px;
      margin-bottom: 15px;
      text-shadow: 0px 0px 1px gold;
      font-family: Times;
    }

    b {
      font-size: 16px;
    }

    footer {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      font-weight: bold;
      font-size: 18px;
      text-transform: uppercase;
      font-style: italic;
    }
</style>