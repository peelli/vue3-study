<template>
  <div>
    <h1 @click="add">{{ count }}</h1>
    {{ x }}
    {{ y }}
    <button @click="toogle">toogle</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useMouse } from '../utils/mouse'
import { useFullscreen } from '@vueuse/core'
const { toogle } = useFullscreen()
let count = ref(1)
let color = ref('red')
function add() {
  count.value++
  color.value = Math.random() < 0.5 ? 'red' : 'blue'
}

const { x, y } = useMouse()
</script>

<style scoped>
h1 {
  color: v-bind(color);
}
</style>
