<script lang="ts" setup>
import { computed } from 'vue';

    const props = defineProps({
        timeSeconds : {
            type: Number,
            default: 0,
        }
    })

    const timeElapsed = computed((): string => {
        return new Date(props.timeSeconds * 1000).toISOString().substr(11,8)
    })
</script>
<template>
  <div class="stopwatch">
    <!-- Cronômetro -->
    <div class="columns is-centered mt-4 stopwatch-layout">
      <div class="column is-narrow">
        <div class="is-flex is-align-items-center is-justify-content-center">
          <!-- Bloco das Horas -->
          <div class="time-box has-background-link has-text-white mx-2">
            {{ timeElapsed.split(':')[0] }}
          </div>

          <!-- Bloco dos Minutos -->
          <div class="time-box has-background-link has-text-white mx-2">
            {{ timeElapsed.split(':')[1] }}
          </div>

          <!-- Bloco dos Segundos -->
          <div class="time-box has-background-link has-text-white mx-2">
            {{ timeElapsed.split(':')[2] }}
          </div>
        </div>
      </div>
    </div>

    <!-- Labels dos campos -->
    <div class="columns is-centered mt-2 stopwatch-layout">
      <div class="column is-narrow has-text-centered">
        <p class="time-label">Hours</p>
      </div>
      <div class="column is-narrow has-text-centered">
        <p class="time-label">Minutes</p>
      </div>
      <div class="column is-narrow has-text-centered">
        <p class="time-label">Seconds</p>
      </div>
    </div>
  </div>
</template>



<style scoped>
.stopwatch .stopwatch-layout {
  display: flex;
}

.stopwatch .time-box {
  width: 60px;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  border-radius: 8px;
  font-weight: bold;
}

.stopwatch .mx-2 {
  margin-left: 8px;
  margin-right: 8px;
}

.stopwatch .time-label {
  font-size: 1rem;
  font-weight: bold;
  color: #4a4a4a;
  margin-top: 8px;
}
</style>


