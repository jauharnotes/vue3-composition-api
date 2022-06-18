<script>
import { reactive, toRefs } from 'vue';
export default {
  setup() {
    const user = reactive({
      name: 'Jauhar',
      age: '25',
    });

    setTimeout(() => {
      user.name = 'Johar';
    }, 2000);

    return {
      ...toRefs(user),
    };
  },
};
</script>

<template>
  <h2>Name People</h2>
  <ol>
    <li>Name: {{ name }}</li>
    <li>Age: {{ age }}</li>
  </ol>
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
