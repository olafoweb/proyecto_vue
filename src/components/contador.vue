<template>

<h1 class="h1counter">Ejemplo de reactividad</h1>
<p class="pcontador">{{ contador }}</p>

<div class="dcontador">
  <p><button class="bcontadori" @click="incrementar">Incrementar</button></p>
</div>   

<div class="dcontador">
  <p><button class="bcontadord" @click="decrementar">Decrementar</button></p>
</div>  

<p class="ptope">El contador al llegar a 20 reinicia en 5</p>
<p class="ptope">El contador al llegar a 1 reinicia en 5</p>
</template>

<script setup>

import {ref} from 'vue';
const contador = ref(5);

const incrementar = () => {
  contador.value++;
  if (contador.value >= 21) {
    contador.value = 5
  }

}

  const decrementar = () => {
    contador.value--;
    if (contador.value <= 0) {
      contador.value = 5
    }
}

</script>

<style scoped>


.h1counter {
  color: rgb(41, 5, 99);
  text-align: center;
}

.pcontador {
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  font-size: 24px;
  text-align: center;
  color: crimson;
}

.dcontador{
  display: flex;
  justify-content: center;
}

.bcontadori {
  font-family: 'Times New Roman', Times, serif;
  font-size: 18px;
  color: rgb(11, 70, 3);
  background-color: aliceblue;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3), 0 1px 3px rgba(0, 0, 0, 0.1);
}

.bcontadord {
  font-family: 'Times New Roman', Times, serif;
  font-size: 18px;
  color: rgb(252, 9, 9);
  background-color: aliceblue;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3), 0 1px 3px rgba(0, 0, 0, 0.1);
}

.ptope {
  text-align: center;
}


</style>
