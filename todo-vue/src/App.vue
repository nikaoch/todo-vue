<script setup>
  const estado = reactive({
    tarefas: [
      {
        titulo: 'Estudar programação',
        finalizada: false
      },
      {
        titulo: 'Estudar repertório',
        finalizada: false
      },
      {
        titulo: 'Guardar dinheiro',
        finalizada: true
      }
    ]
  })
</script>

<template>
  <div class="container">
    <header class="p-5 mt-4 mb-4 rounded-3 bg-light">
      <h1>Minhas tarefas</h1>
      <p>
        Você possui 7 tarefas pendentes.
      </p>
    </header>
    <form>
      <div class="row">
        <div class="col">
          <input type="text" placeholder="Digite a descrição da tarefa" class="form-control">
        </div>
        <div class="col-md-1">
          <button class="btn btn-primary" type="submit">Cadastrar</button>
        </div>
        <div class="col-md-2">
          <select class="form-control">
            <option value="todas">Todas as tarefas</option>
            <option value="pendentes">Pendentes</option>
            <option value="finalizadas">Finalizadas</option>
          </select>
        </div>
      </div>
    </form>
    <ul class="list-group mt-4">
      <li class="list-group-item" v-for="tarefa in estado.tarefas">
        <input :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label class="ms-3" :for="tarefa.titulo">
          {{ tarefa.titulo }}
        </label>
      </li>
    </ul>
  </div>
</template>

<style scoped>
</style>
