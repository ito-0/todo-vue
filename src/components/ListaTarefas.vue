<script setup>
    const props = defineProps(['tarefas'])
</script>

<template>
    <div class="row">
        <div class="col-12" v-for="tarefa in props.tarefas" :key="tarefa.id">
            <div class="card mt-3">
                <div class="card-body">
                    <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                    :id="tarefa.titulo" type="checkbox">
                    <label :class="{ done: tarefa.finalizada }" :for="tarefa.titulo">
                    {{ tarefa.titulo }}
                    </label>
                </div>
            </div>
        </div>
    </div>
    <p v-if="props.tarefas.length === 0">Não existem tarefas pendentes.</p>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>