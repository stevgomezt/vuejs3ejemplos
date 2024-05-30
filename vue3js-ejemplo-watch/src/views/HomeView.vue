<script setup>
import { ref, watch } from "vue";

// Variable reactiva para almacenar la entrada del usuario
const userInput = ref("");

// Variable reactiva para almacenar la longitud del texto
const textLength = ref(0);

// Función que observa cambios en userInput y actualiza textLength
watch(userInput, (newValue, oldValue) => {
    textLength.value = newValue.length;
});
</script>

<template>
    <div>
        <input v-model="userInput" placeholder="Escribe algo..." />
        <p>{{ userInput }}</p>
        <p>Longitud del texto: {{ textLength }}</p>
    </div>
</template>
