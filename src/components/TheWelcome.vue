<template>
  <div>
    <h1>Masukkan kata red, maka hurufnya akan berubah warna</h1>
    <input type="text" v-model="inputText" :class="{ 'input-red': isRed }" @input="handleInput">
    <p :style="{ color: textColor }">{{ inputText }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const inputText = ref('')
const isRed = ref(false)
const textColor = ref('black')

const handleInput = () => {
  if (inputText.value === 'red') {
    isRed.value = true
    textColor.value = 'red'
  } else {
    isRed.value = false
    textColor.value = 'black'
  }
}
</script>

<style scoped>
.input-red {
  border-color: red;
}
</style>
