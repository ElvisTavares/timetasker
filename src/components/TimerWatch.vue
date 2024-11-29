<script lang="ts" setup>
import StopWatch from './StopWatch.vue';
</script>
<template>
    <!-- <StopWatch :timeSeconds="timeSeconds"/> -->
    <StopWatch /> 
    <!-- BUTTON -->
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
</template>