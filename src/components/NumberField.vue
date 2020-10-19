<template>
  <input type="number" v-model="innerValue" />
</template>

<script>
export default {
  name: "NumberField",
  props: {
    value: Number,
    id: Number,
  },
  computed:{
    innerValue:{
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
  input[type="Number"]{
    border: none;
    border-bottom: 1px solid gray;
    outline: none;
    font-size: 16px;
  }
</style>