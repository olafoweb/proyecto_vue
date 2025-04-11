<template>
<h1>Ejemplo de reactividad</h1>
<p>{{ contador }}</p>
<p><button @click="incrementar">Incrementar</button></p>
<p><button @click="decrementar">DEcrementar</button></p>
   
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

* {
  text-align: center;
}

h1 {
  color: blue;
}

p {
  color: rgb(5, 0, 0);
}

button {
  color: rgb(163, 6, 6);
  background-color: rgb(248, 252, 9);
}

</style>
