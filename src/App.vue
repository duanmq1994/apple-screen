<template>
  <div id="app">
    <list-setup :name="number" />
    <button @click="handleClick">Change number</button>
    <HelloWorld />
    <button>Change date</button>
  </div>
</template>

<script>
import { ref, provide, reactive } from 'vue';
import ListSetup from './components/ListSetup';
import HelloWorld from './components/HelloWorld';
export default {
  name: 'App',
  components: {
    ListSetup,
    HelloWorld,
  },
  setup() {
    const number = ref(0);
    const handleClick = () => {
      number.value += 1;
    };
    const message = ref('Hola!');
    const date = reactive({
      month: 5,
      day: 11,
    });
    provide('message', message);
    provide('date', date);
    return {
      number,
      handleClick,
    };
  },
};
</script>

<style></style>
