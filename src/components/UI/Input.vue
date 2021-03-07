<template>
  <div class="input">
    <label>
      <span>{{ label }}</span>
      <input 
        type="text"
        :value="inputValue"
        v-on="$listeners"
        v-bind="$attrs"
      >
    </label>
  </div>
</template>
<script>
export default {
  inheritAttrs: false,
  name: "Input",
  props: {
    value: {
      type: String,
      required: false,
      default: ""
    },
    label: {
      type: String,
      default: "Label"
    }
  },
  computed: {
    inputValue: {
      get() {
        return this.value
      },
      set(newVal) {
        this.$emit("input", newVal);
      }
    },
  }
}
</script>