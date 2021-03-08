<template>
  <div class="button">
    <button
      :class="classes"
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
    },
    active: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    classes() {
      return {
        'button__btn': true,
        'button__active': this.active,
      };
    },
  }
}
</script>
<style lang="scss">
.button {
  &__btn {
    width: 100%;
    max-width: 170px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 6px;
    padding-right: 6px;
    border-radius: 3px;
    border: none;
    outline: none;
    color: #fff;
    background-color: #192B85;
    white-space: nowrap;
  }

  &__active {
    background-color: #bbb;
    pointer-events: none;
  }
}
</style>