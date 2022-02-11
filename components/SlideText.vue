<template>
  <div
    style="position: absolute; overflow: none; transform: scaleX(-1);  white-space: nowrap;"
    :style="[`top: ${y}px;`, `left: ${x + xMove}px;`]"
    v-bind="$attrs"
  >{{ text }}</div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue'
const props = defineProps<{
  text: string
  y: number
  x: number
  speed: number
  max: number
}>()
const emit = defineEmits<{
  (event: 'finish'): void
}>()
const xMove = ref(0)
const interval = setInterval(() => xMove.value += props.speed, 1)
watch(xMove, () => {
  if (xMove.value > props.max) {
    clearInterval(interval)
    emit('finish')
  }
})
</script>