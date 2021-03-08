<template>
  <div class="field">
    <div class="field__body">
      <slot />
    </div>
  </div>
</template>
<script>
export default {
  name: "FieldCoord",
}
</script>
<style lang="scss">
.field {
  width: 100%;
  height: 350px;
  border-left: 1px solid #bbb;
  border-bottom: 1px solid #bbb;

  &__body {
    width: 100%;
    height: 100%;
    position: relative;
  }
}
</style>