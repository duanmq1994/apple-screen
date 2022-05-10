<template>
  <div id="app">
    <list-setup :name="number" />
    <button @click="handleClick">Click to Change</button>
  </div>
</template>

<script>
import ListSetup from './components/ListSetup';
export default {
  name: 'App',
  data() {
    return {
      number: 0,
    };
  },
  components: {
    ListSetup,
  },
  methods: {
    handleClick() {
      this.number += 1;
    },
  },
};
</script>

<style></style>
