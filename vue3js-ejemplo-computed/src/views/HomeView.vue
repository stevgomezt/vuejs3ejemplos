<script setup>
import { ref, computed } from "vue";

// Crear una referencia reactiva para la lista de tareas
const tasks = ref([
    { id: 1, text: "Aprender Vue.js", completed: false },
    { id: 2, text: "Escribir documentación", completed: true },
    { id: 3, text: "Hacer un proyecto", completed: false },
]);

// Propiedad computada para contar las tareas pendientes
const pendingTasksCount = computed(() => {
    return tasks.value.filter((task) => !task.completed).length;
});

// Función para añadir una nueva tarea
const addTask = () => {
    const newTaskId = tasks.value.length + 1;
    tasks.value.push({
        id: newTaskId,
        text: `Nueva tarea ${newTaskId}`,
        completed: false,
    });
};
</script>

<template>
    <div class="task-list">
        <h1>Lista de Tareas</h1>
        <ul>
            <li v-for="task in tasks" :key="task.id">
                {{ task.text }} <span v-if="task.completed">(Completada)</span>
            </li>
        </ul>
        <p>Tareas pendientes: {{ pendingTasksCount }}</p>
        <button @click="addTask">Añadir tarea</button>
    </div>
</template>

<style scoped>
.task-list {
    font-family: Arial, sans-serif;
    padding: 20px;
}

h1 {
    font-size: 2em;
    margin-bottom: 10px;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    margin: 5px 0;
    font-size: 1.2em;
}

button {
    margin-top: 20px;
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
