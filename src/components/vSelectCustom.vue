<template lang="pug">
  div
    span.d-block.outside-label(v-if="outsideLabel")  {{ outsideLabel }}
    v-select.custom-select(v-bind='$attrs', v-on='$listeners', append-icon="$arrowdown", solo, flat, background-color="border", height="52", hide-details)
      template(v-for="slot in Object.keys($scopedSlots)", v-slot:[slot])
        slot(:name="slot")
</template>

<style lang="scss">
  .v-select.custom-select {
    .v-label {
      color: var(--v-label-base);
    }
  }
</style>

<style scoped lang="scss">
  .outside-label {
    font-size: 12px;
    line-height: 16px;
    color: var(--v-dark-base);
    margin-left: 18px;
    margin-bottom: 6px;
  }
</style>

<script>
export default {
  name: 'vSelectCustom',
  inheritAttrs: false,
  props: {
    outsideLabel: {type: String, default: undefined}
  }
}
</script>
