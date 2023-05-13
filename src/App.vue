
<script setup>

import { ref } from 'vue'; 

// const saludo = "Hola mundo";
// const complemento = ref("Cruel");
// complemento.value = "Bonito";
const tittle = ref("Mega ejemplo");
const solicitudes = ref(0);
const aumentar = () => {
  solicitudes.value++;
}
const disminuir = () => {
  if(solicitudes.value > 0){
    solicitudes.value--;
  }
}
</script>

<template>
  <div class="content">
    <h2>{{ tittle }}</h2>
    <div class="user">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M406.5 399.6C387.4 352.9 341.5 320 288 320H224c-53.5 0-99.4 32.9-118.5 79.6C69.9 362.2 48 311.7 48 256C48 141.1 141.1 48 256 48s208 93.1 208 208c0 55.7-21.9 106.2-57.5 143.6zm-40.1 32.7C334.4 452.4 296.6 464 256 464s-78.4-11.6-110.5-31.7c7.3-36.7 39.7-64.3 78.5-64.3h64c38.8 0 71.2 27.6 78.5 64.3zM256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zm0-272a40 40 0 1 1 0-80 40 40 0 1 1 0 80zm-88-40a88 88 0 1 0 176 0 88 88 0 1 0 -176 0z"/></svg>

      <div v-if="solicitudes != 0" class="Notification">
        {{ solicitudes }}
      </div>
    </div>
    <br>
    <div class="buttons">
      <button @click="disminuir">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"><path d="M169.4 470.6c12.5 12.5 32.8 12.5 45.3 0l160-160c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L224 370.8 224 64c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 306.7L54.6 265.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l160 160z"/></svg>
      </button>
      <button @click="aumentar">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"><path d="M214.6 41.4c-12.5-12.5-32.8-12.5-45.3 0l-160 160c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L160 141.2V448c0 17.7 14.3 32 32 32s32-14.3 32-32V141.2L329.4 246.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3l-160-160z"/></svg>
      </button>
    </div>

    <div class="Mensajes">
      <input type="text" v-model="tittle">
      <div class="mg" v-show="solicitudes > 0">
        <h3>Woojo!!! Tienes solicitudes</h3>
      </div>
    </div>

  </div>
  
</template>

<style scoped>
.content{
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 200px;
  width: 300px;
}
  .user{
    position: relative;
    width: 100px;
    height: 100px;
  }
  .Notification{
    position: absolute;
    background-color: red;
    font-size: x-large;
    color: white;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    text-align: center;
    top: -12px;
    right: -12px;
  }
  .buttons{
    width: 150px;
    display: flex;
    justify-content: space-around;
  }
  .buttons button{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 40px;
    width: 40px;
    background-color: #7d93a6;
    opacity: 90%;
    box-shadow: 0 0 3px black;
    border-radius: 5px;
  }
  .Mensajes{
    margin-top: 10px;
    width: 300px;
    height: 100px;
  }
  .mg{
    margin-top: 5px;
    color: #7d93a6;
  }
  

</style>