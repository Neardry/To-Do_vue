<script setup>
    const props = defineProps(['tarefasFiltradas'])
</script>

<template>
        <ul v-if="tarefasFiltradas.length > 0" class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefasFiltradas ">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" for=""> {{ tarefa.titulo }}</label>
        </li>
    </ul>
    <h3 v-else class="mt-2">Não há tarefas </h3>
</template>

<style scoped>

    .done {
        text-decoration: line-through;
    }

</style>