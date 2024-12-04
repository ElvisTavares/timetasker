<script lang="ts" setup>
import StopWatch from './StopWatch.vue';
import { ref, defineEmits } from 'vue';

const emit = defineEmits(['timerCompleted'])

const timeSeconds = ref(0)
const stopWatch = ref<number | null>(null)
const timerRun = ref(false)


const play = () => {
  timerRun.value = true
  stopWatch.value = setInterval(() => {
    timeSeconds.value += 1

  }, 1000)
}

const stop = () => {
  timerRun.value = false

  if (stopWatch.value !== null) {
    clearInterval(stopWatch.value)
    stopWatch.value = null
  }

  emit('timerCompleted', timeSeconds.value)
  timeSeconds.value = 0
}
</script>
<template>
    <!-- <StopWatch :timeSeconds="timeSeconds"/> -->
    <StopWatch :timeSeconds="timeSeconds" /> 
    <!-- BUTTON -->
        <!-- Botões -->
        <div class="buttons is-centered mt-4">
        <button class="button is-info is-medium" @click="play" :disabled="timerRun">
          <span class="icon">
            <i class="fas fa-play"></i>
          </span>
          <span>Play</span>
        </button>
        <button class="button is-danger is-medium" @click="stop" :disabled="!timerRun">
          <span class="icon">
            <i class="fas fa-stop"></i>
          </span>
          <span>Stop</span>
        </button>
      </div>
</template>