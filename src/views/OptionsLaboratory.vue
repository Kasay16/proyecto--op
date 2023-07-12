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

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },

  methods: {
    increment() {
      this.count++;
    },
  },
};
</script>
