<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <span>{{ date.month }}-{{ date.day }}</span>
  </div>
</template>

<script>
import { inject } from 'vue';
export default {
  name: 'HelloWorld',
  setup() {
    const msg = inject('message');
    const date = inject('date');
    return {
      msg,
      date,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
