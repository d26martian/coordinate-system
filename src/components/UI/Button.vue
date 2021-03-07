<template>
  <div class="button">
    <button
      class="button__btn"
      @click="$emit('onClick')"
      v-on="$listeners"
      v-bind="$attrs"
    >
      {{ text }}
    </button>
  </div>
</template>
<script>
export default {
  inheritAttrs: false,
  name: "Button",
  props: {
    text: {
      type: String,
      default: "Send"
    }
  },
}
</script>
<style lang="scss">
.button {
  &__btn {
    width: 100%;
    max-width: 120px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 6px;
    padding-right: 6px;
    border: none;
    outline: none;
    color: #fff;
    background-color: #192B85;
    white-space: nowrap;
  }
}
</style>