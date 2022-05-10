<template>
  <span>{{ hello }}</span>
  <span>{{ computedName }}</span>
</template>

<script>
export default {
  name: 'List',
  data() {
    return {
      hello: 'Hello! ',
    };
  },
  props: {
    name: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    computedName() {
      return 'No. ' + this.name;
    },
  },
  watch: {
    name: 'changeName',
  },
  methods: {
    changeName() {
      if (this.name % 2 === 0) {
        this.hello = 'Hello! ';
      } else {
        this.hello = 'Oh! ';
      }
    },
  },
};
</script>

<style></style>
