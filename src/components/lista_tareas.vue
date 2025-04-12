<template>

    <div>
        <h2>Lista de Tareas</h2>
        <input type="text" v-model="nueva_tarea" @keyup.enter="add_tarea">
        <p>{{ nueva_tarea }}</p>
        <ul>
            <li v-for="(tarea, index) in tareas" :key="index">
                {{ tarea }}
                <button @click="borrar">Borrar</button>
            </li>
        </ul>
    </div>

</template>

<script setup>

import {ref} from 'vue';
const tareas = ref ([]);
const nueva_tarea = ref ('');
const add_tarea = () => {
    tareas.value.push(nueva_tarea.value);
    nueva_tarea.value = '';
}

const borrar=(index) => {
    tareas.value.splice(index,1);
}
</script>

<style scoped></style>