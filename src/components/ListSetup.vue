<template>
  <span>{{ hello }}</span>
  <span>{{ computedName }}</span>
</template>

<script>
import { ref, watch, toRefs, computed } from 'vue';
export default {
  name: 'ListSetup',
  props: {
    name: {
      type: Number,
      default: 0,
    },
  },
  setup(props) {
    const { name } = toRefs(props);
    const hello = ref('Hello! ');
    const changeName = () => {
      if (name.value % 2 === 0) {
        hello.value = 'Hello! ';
      } else {
        hello.value = 'Oh! ';
      }
    };
    const computedName = computed(() => {
      return 'No. ' + name.value;
    });
    watch(name, changeName);
    return {
      hello,
      changeName,
      computedName,
    };
  },
};
</script>

<style></style>
