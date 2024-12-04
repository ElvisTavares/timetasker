<template>
 
<main>
  <div class="column is-three-quarter conteudo">
 <div class="list">
  <TaskForm @isSavetask="saveTask"/>
  <TaskList v-for="(task, index) in tasks" :key="index" :task="task"/>
 </div>
 </div>
</main>
</template>

<script lang="ts" setup>
import { ref, computed } from 'vue';
import TaskForm from './components/TaskForm.vue';
import TaskList from './components/TaskList.vue';
import ITask from '@/interfaces/ITask';

const tasks = ref<ITask[]>([])

function saveTask(task: ITask) {
  tasks.value.push(task)
}
</script>

<style scoped>
.list {
  padding: 1.25rem;

}
main {
  --bg-primario: #fff;
  --texto-primario: #000;

}

.conteudo {
  background-color: var(--bg-primario);
}
</style>
