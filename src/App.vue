<script setup>

import { ref } from 'vue';

import fotochip from "./assets/chip.png"
import fotochip2 from "./assets/chip2.png"

import logovisa from "./assets/visa.png"
import logomastercard from "./assets/mastercard.png"


let tituloDeLaTarjeta = ref("");
let numero = ref("");
let fechaDeExpiracion = ref("");
let Propietario = ref("");
let tipoDeTarjeta = ref("");
let chips = ref("");


</script>

<template>
 <div id="app">
      <form>
        <div>
          <label>Título de la tarjeta: </label>
          <input  type="text" v-model="tituloDeLaTarjeta"/>
        </div>

        <div>
          <label >Chip SRC: </label>
          <select v-model="chips">
        <option value="chip1">Chip1</option>
        <option value="chip2">Chip2</option>
      </select>
        </div>

        <div>
          <label>Número: </label>
          <input type="text" v-model="numero"/>
        </div>

        <div>
          <label>Fecha de expiración: </label>
          <input type="text" v-model="fechaDeExpiracion"/>
        </div>

        <div>
          <label>Propietario: </label>
          <input type="text" v-model="Propietario"/>
        </div>

        <div>
          <label>Tipo de tarjeta SRC: </label>
          <select v-model="tipoDeTarjeta">
        <option value="visa"> Visa </option>
        <option value="mastercard"> Mastercard </option>
      </select>
        </div>
      </form>

      <div class="carnet">
        <h3>{{ tituloDeLaTarjeta }}</h3>
        <img v-show="chips === 'chip1'" width="40" :src="fotochip" alt="" />
        <img v-show="chips === 'chip2'" width="40" :src="fotochip2" alt="" />
        <div>
          <h2>{{ numero }}</h2>
          <span>Fecha Exp: <b>{{ fechaDeExpiracion }}</b></span>
        </div>
        <footer>
          <span>{{ Propietario }}</span>
          <img v-show="tipoDeTarjeta === 'visa'" :src="logovisa" width="60" />
    <img v-show="tipoDeTarjeta === 'mastercard'" :src="logomastercard" width="60" />
        </footer>
      </div>
    </div>
</template>

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
