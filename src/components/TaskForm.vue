<template>
<div>
    <h1>Formulario</h1>
    <section class="section has-text-centered">
    <div class="container">
      <!-- Título -->
      <h1 class="title is-size-2 has-text-primary">TimeTasker</h1>

      <!-- Cronômetro -->
      <div class="columns is-centered mt-4">
        <div class="column is-narrow">
          <div class="box has-background-primary-light p-4">
            <div class="is-flex is-justify-content-center is-align-items-center">
              <div
                v-for="n in 6"
                :key="n"
                class="time-box has-background-info has-text-white has-text-weight-bold"
              >
                0
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Campo de texto -->
      <div class="field mt-4">
        <div class="control">
          <input
            class="input is-medium has-text-centered"
            type="text"
            placeholder="Digite a tarefa"
          />
        </div>
      </div>

      <!-- Botões -->
      <div class="buttons is-centered mt-4">
        <button class="button is-info is-medium">
          <span class="icon">
            <i class="fas fa-play"></i>
          </span>
          <span>Play</span>
        </button>
        <button class="button is-danger is-medium">
          <span class="icon">
            <i class="fas fa-stop"></i>
          </span>
          <span>Stop</span>
        </button>
      </div>

      <!-- Lista de tarefas -->
      <div class="box has-background-light mt-6">
        <p class="is-size-4 has-text-grey-dark">Lista das tarefas</p>
      </div>
    </div>
  </section>
</div>
</template>

<script setup>

</script>

<style scoped>
.time-box {
  width: 3rem;
  height: 3rem;
  margin: 0 0.3rem;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.5rem;
  border-radius: 0.25rem;
}
</style>