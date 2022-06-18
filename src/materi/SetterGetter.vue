<script>
import { reactive, ref, computed, toRefs } from 'vue';
export default {
  setup() {
    const counter = reactive({
      nilai: 0,
    });

    const add = () => {
      result.value = 5;
      counter.nilai++;
    };

    const min = () => {
      result.value = 5;
      counter.nilai--;
    };

    const addNum = ref(1);

    const result = computed({
      get: () => counter.nilai + addNum.value,
      set: (val) => (addNum.value = val),
    });

    return {
      ...toRefs(counter),
      add,
      min,
      result,
    };
  },
};
</script>

<template>
  <h2>Count: {{ nilai }}</h2>
  <button @click="add">ADD</button>
  <button @click="min">MIN</button>
  <h2>Result: {{ result }}</h2>
</template>
