<template>
  <random-fall-texts
    text="🐫"
    :speed="speed"
    :max="max / 2"
    :interval="interval * 2"
    class="text-6xl opacity-50"
  />
  <random-fall-texts
    text="🐪"
    :speed="speed"
    :max="max / 2"
    :interval="interval * 2"
    class="text-6xl opacity-50"
  />
  <div class="absolute grid gap-2 grid-cols-2 text-right opacity-40" style="bottom: 60px; left: 0px;">
    <div class="col-span-2">ラクダ調節機能</div>
    <div>
      <label for="interval" class="pr-2">interval</label>
    </div>
    <div>
      <input v-model.number="interval" type="range" id="interval"  max="500" />
    </div>
    <div>
      <label for="speed" class="pr-2">speed</label>
    </div>
    <div>
      <input v-model.number="speed" type="range" id="speed" max="1000" />
    </div>
    <div>
      <label for="max" class="pr-2">max</label>
    </div>
    <div>
      <input v-model.number="max" type="range" id="max" max="300" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const interval = ref(200)
const max = ref(50)
const speed = ref(200)
</script>