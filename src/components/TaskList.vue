<script lang="ts" setup>
import { PropType } from 'vue';
import StopWatch from './StopWatch.vue';
import ITask from '@/interfaces/ITask';

  defineProps({
    task: {
      type: Object as PropType<ITask>,
      required: true
    }
  })
</script>
<template>

<div class="box has-background-light mt-6">
       
        <div>
          <p>
            {{ task.description || 'Tarefa sem descrição' }}
          </p>
          
           
            <StopWatch :timeSeconds="task.durationSeconds" />
          
        </div>
</div>
</template>

<style scoped>

</style>