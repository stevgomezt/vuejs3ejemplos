<script setup>
import { ref, computed, reactive, watch } from "vue";

// Definimos una referencia reactiva para el contador
const contador = ref(0);

// Definimos una propiedad computada para calcular el cuadrado del contador
const contadorCuadrado = computed(() => contador.value ** 2);

// Creamos un objeto reactivo para almacenar el estado del contador
const estado = reactive({
    valor: 0,
});

// Observamos cambios en la propiedad valor del objeto estado
watch(
    () => estado.valor,
    (nuevoValor, antiguoValor) => {
        contador.value = nuevoValor;
    }
);

// Función para incrementar el contador
const incrementar = () => {
    estado.valor++;
};

// Función para decrementar el contador
const decrementar = () => {
    estado.valor--;
};
</script>

<template>
    <div>
        <h1>Contador</h1>
        <p>Valor del contador: {{ contador }}</p>
        <p>Cuadrado del contador: {{ contadorCuadrado }}</p>
        <button @click="incrementar">Incrementar</button>
        <button @click="decrementar">Decrementar</button>
    </div>
</template>
