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