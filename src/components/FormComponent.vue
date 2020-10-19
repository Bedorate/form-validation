<template>
  <div class="form-component">
      <div class="form-component-label">{{form.label}}</div>
        <div class="form-component-content">
          <div class="form-component-input">
            <keep-alive>
              <component
                :is="form.formType"
                :value="form.value"
                :id="form.id"
                :data="form.data"
                @change-value="changeValue"
              />
            </keep-alive>
          </div>
        <div class="form-component-validation">{{validationMessage[form.keyName]}}</div>
        </div>
</div>
</template>

<script>
import TextField from "@/components/TextField.vue";
import NumberField from "@/components/NumberField.vue";
import RadioButton from "@/components/RadioButton.vue";
import SelectBox from "@/components/SelectBox.vue";
import CheckBox from "@/components/CheckBox.vue";

export default {
  name: "FormComponent",
  components: {
    TextField,
    NumberField,
    RadioButton,
    SelectBox,
    CheckBox,
  },
  props: {
    form: Object,
    validationMessage: Object,
  },
  methods: {
    changeValue(key, value){
      this.$emit("change-value", key, value);
    },
  }
}
</script>

<style lang="scss">
.form-component {
      width: 100%;
      display: flex;
      margin-bottom: 16px;
      &-label {
        width: 28%;
        font-size: 20px;
        margin-right: 16px;
      }
      &-content {
        flex: 1;
        .form-component-input {
          display: flex;
          align-items: center;
          justify-content: flex-start;
        }
        .form-component-validation{
          height: 36px;
          display: flex;
          align-items: flex-end;
          color: red;
        }
      }
    }
</style>