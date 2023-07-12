<template>
  <v-container>
    <v-row justify="center">
      <h1>Contador: {{ count }}</h1>
    </v-row>
    <v-row justify="center">
      <v-btn @click="increment">Incremetar</v-btn>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue'

// reactive state
const count = ref(0)

// functions that mutate state and trigger updates
function increment() {
  count.value++
}
</script>
