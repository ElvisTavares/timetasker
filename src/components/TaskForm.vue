<script lang="ts" setup>
import TaskList from './TaskList.vue';
import TimerWatch from './TimerWatch.vue';
import { ref, defineEmits } from 'vue';

const emit = defineEmits(['isSavetask'])
const description = ref('')
const stopTask = ( timeElapsed: number): void => {
  emit('isSavetask', {
    durationSeconds: timeElapsed,
    description: description.value
  })

  description.value = ''
}
</script>

<template>
<div>
    <section class="section has-text-centered">
    <div class="container">
      <!-- Título -->
      <h1 class="title is-size-2 has-text-primary">TimeTasker</h1>

     <!-- CRONOMETRO -->
      <TimerWatch @timerCompleted="stopTask"/>
      <!-- Campo de texto -->
      <div class="field mt-4">
        <div class="control">
          <input
            class="input is-medium has-text-centered"
            type="text"
            placeholder="Digite a tarefa"
            v-model="description"
          />
        </div>
      </div>

   

  
    </div>
  </section>
</div>
</template>



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