<template>
 <TaskForm/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TaskForm from './components/TaskForm.vue';


export default defineComponent({
  name: 'App',
  components: {
    TaskForm
  }
});
</script>

<style>

</style>
