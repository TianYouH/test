<template>
  <!-- <input
    type="text"
    :value="customModel"
    @input="$emit('customEvent', $event.target.value)"
  /> -->
  <input
    type="text"
    :value="customModel"
    @input="$emit('update:customModel', $event.target.value)"
  />
</template>
<script>
export default {
  name: 'CustomModel',
  // model: {
  //   prop: 'customModel',
  //   event: 'customEvent'
  // },
  emits: ['update:customModel'],
  props: {
    customModel: {
      type:  String,
      default() {
        return ""
      }
    }
  }
};
</script>
<style lang="scss" scoped></style>
