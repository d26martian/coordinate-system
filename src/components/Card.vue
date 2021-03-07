<template>
  <div class="card">
    <div class="card__header">
      <div class="card__title">
        <slot name="title" />
      </div>
    </div>
    <div class="card__content">
      <slot name="content" />
    </div>
  </div>
</template>
<script>
export default {
  name: 'Card'
}
</script>
<style lang="scss">
.card {
  max-width: 350px;
  width: 100%;
  border: 1px solid #eee;
  padding: 30px 15px;
  box-shadow: 0 0 4px #ccc;

  &__header {
    border-bottom: 1px solid #ccc;
    margin-bottom: 20px;
  }

  &__title {
    font-size: 20px;
    font-weight: 400;
  }
}
</style>