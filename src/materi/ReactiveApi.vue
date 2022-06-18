<script>
import { reactive } from 'vue';
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
      user,
    };
  },
};
</script>

<template>
  <h2>Name People</h2>
  <ol>
    <li>Name: {{ user.name }}</li>
    <li>Age: {{ user.age }}</li>
  </ol>
</template>
