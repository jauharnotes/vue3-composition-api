<script>
import { reactive, toRef } from 'vue';
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
      ...toRef(user),
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
