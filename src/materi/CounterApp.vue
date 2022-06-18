<script>
import { reactive, toRefs } from 'vue';
export default {
  setup() {
    const counter = reactive({
      nilai: 0,
    });

    const add = () => {
      counter.nilai++;
    };

    const min = () => {
      counter.nilai--;
    };

    return {
      ...toRefs(counter),
      add,
      min,
    };
  },
};
</script>

<template>
  <h2>{{ nilai }}</h2>
  <button @click="add">ADD</button>
  <button @click="min">MIN</button>
</template>
