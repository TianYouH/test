<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<script>
import CustomModel from './CustomModel.vue'
export default {
  components: {
    CustomModel
  },  
  data() {
    return {
      value: '5215',
      obj: {
        a: 3,
        b: 4,
      },
    };
  },
  methods: {
    addCount() {
      this.count ++;
      // this.obj.a++;
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
  <h3>自定义v-model测试</h3>
  {{ value }}
  <CustomModel v-model:customModel="value" ></CustomModel>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
