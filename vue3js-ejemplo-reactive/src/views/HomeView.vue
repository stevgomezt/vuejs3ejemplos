<script setup>
import { ref } from "vue";

// Crear una referencia reactiva para el conteo de clics
const count = ref(0);

// Función para incrementar el conteo de clics
const increment = () => {
    count.value++;
};
</script>

<template>
    <div class="counter">
        <p>Has hecho clic {{ count }} veces.</p>
        <button @click="increment">Haz clic</button>
    </div>
</template>

<style scoped>
.counter {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    font-family: Arial, sans-serif;
}

p {
    font-size: 1.5em;
    margin-bottom: 20px;
}

button {
    padding: 10px 20px;
    font-size: 1em;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}
</style>
