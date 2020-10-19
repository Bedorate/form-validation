<template>
  <div class="checkbox">
    <div v-for="(item, index) in data" :key="index" class="checkbox-button">
      <label>
        <input
          type="checkbox"
          :checked="value.includes(item.id)"
          @change="atChange(item.id)"
        />
        {{ item.label }}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "CheckBox",
  props: {
    value: Array,
    id: Number,
    data: Array,
  },
  methods: {
    atChange(itemId) {
      this.$emit(
        "change-value",
        this.id,
        this.value.includes(itemId) ? this.value.filter((v) => v !== itemId)
          : [...this.value, itemId]
      );
    },
  },
};
</script>

<style lang="scss" scoped>
.checkbox {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  &-button {
    margin-right: 8px;
  }
}
</style>