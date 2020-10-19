<template>
  <div class = "radio">
    <div v-for="(item, index) in data" :key="index" >
      <label>
      <input type = "radio" :value="item.id" v-model="innerValue" /> {{item.label}}
      </label>
  </div>
  </div>
</template>

<script>
export default {
  name: "RadioButton",
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