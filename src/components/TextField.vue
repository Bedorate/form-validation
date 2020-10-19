<template>
  <input type="text" v-model="innerValue" />
</template>

<script>
export default {
  name: "TextField",
  props: {
    value: String,
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
  input[type="text"]{
    border: none;
    border-bottom: 1px solid gray;
    outline: none;
    font-size: 16px;
  }
</style>