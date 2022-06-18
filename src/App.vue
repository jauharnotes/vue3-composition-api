<script>
import { ref } from 'vue';
export default {
  setup() {
    const message = ref('hello');

    setTimeout(() => {
      message.value = 'nuwun';
    }, 2000);

    return {
      message,
    };
  },
};
</script>

<template>
  <h2>{{ message }}</h2>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
