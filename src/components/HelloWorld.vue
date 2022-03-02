<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<script>
export default {
  data() {
    return {
      obj: {
        a: 3,
        b: 4,
      },
    };
  },
  methods: {
    addCount() {
      // this.count ++;
      this.obj.a++;
      console.log("jiji");
    },
  },
  watch: {
    count: (newVal, oldVal) => {
      console.log("新值：", newVal);
      console.log("旧值：", oldVal);
    },
    obj: {
      handler: (newVal, oldVal) => {
        console.log("新值：", newVal);
        console.log("旧值：", oldVal);
      },
      deep: true,
    },
  },
};
</script>

<template>
  <button type="button" @click="addCount">count is: {{ count }}</button>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
