<template lang="pug">
  v-tabs.v-tabs-custom(v-bind='$attrs', v-on='$listeners', height="66", @change="onChange")
    template(v-for="slot in Object.keys($scopedSlots)", v-slot:[slot])
      slot(:name="slot")
</template>

<style lang="scss">
  .v-tabs.v-tabs-custom {
    .v-tabs-slider-wrapper {
      height: 4px !important;
      color: var(--v-dark-base);
    }
  }
</style>

<script>
export default {
  name: 'vTabsCustom',
  inheritAttrs: false,
  methods: {
    onChange(tabIndex){
      this.$emit("input", tabIndex)
    }
  }
}
</script>
