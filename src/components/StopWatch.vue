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
    <section>
        <strong class="display">{{ timeElapsed }}</strong>
    </section>
     <!-- Cronômetro -->
     <div class="columns is-centered mt-4">
        <div class="column is-narrow">
          <div class="box has-background-primary-light p-4">
            <div class="is-flex is-justify-content-center is-align-items-center">
              <div
               
                class="time-box has-background-info has-text-white has-text-weight-bold"
              >
              {{ timeElapsed }}
              </div>
            </div>
          </div>
        </div>
      </div>
</template>

<style scoped>
.display {
    color: var(--texto-primario)
}
</style>
