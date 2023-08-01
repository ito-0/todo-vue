<script setup>
    const props = defineProps(['cadastroTarefas', 'tarefasTemp', 'trocarFiltro', 'editaTarefasTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastroTarefas">
        <div class="row align-items-center">
        <div class="col-md-auto col-12">
            <input :value="props.tarefasTemp" @change="props.editaTarefasTemp" required type="text" placeholder="Descrição" class="form-control">
        </div>
        <div class="col-md-auto col-12">
            <button type="submit" class="btn btn-secondary">Cadastrar</button>
        </div>
        <div class="col-md-auto col-12 mt-2 mt-md-0">
            <select @change="props.trocarFiltro" class="form-control">
                <option value="todas">Todas</option>
                <option value="pendentes">Pendentes</option>
                <option value="finalizadas">Finalizadas</option>
            </select>
        </div>
        </div>
    </form>
</template>