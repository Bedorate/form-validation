<template>
  <select v-model="innerValue">
    <option v-for="(item, index) in data" :key="index" :value="item.id">
      {{ item.label }}
  </option>
  </select>
</template>

<script>
export default {
  name: "SelectBox",
  props: {
    value: Number,
    id: Number,
    data: Array,
  },
  computed: {
    innerValue: {
      get(){
        return this.value;
      },
      set(value){
        this.$emit("change-value", this.id, value);
      },
    },
  },
};
</script>

<style>

</style>