<script>
import { reactive, ref, computed, watchEffect, toRefs } from 'vue';
export default {
  setup() {
    const counter = reactive({
      nilai: 0,
      foo: 'bar',
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

    watchEffect(
      () => {
        console.log(counter.nilai);
      },
      {
        onTrigger(e) {
          console.log(e);
        },
        onTrack(e) {
          console.log(e);
        },
      }
    );

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
