<template lang="pug">
  v-tab.v-tab-custom.v-tab-custom__item(v-bind='$attrs', v-on='$listeners', :ripple="false", @change="onChange")
    template(v-for="slot in Object.keys($scopedSlots)", v-slot:[slot])
      slot(:name="slot")
</template>

<style lang="scss">
.v-tab.v-tab.v-tab-custom {
  padding: 0;
  min-width: unset;
  text-transform: unset;
  font-size: 19px;
  font-weight: unset;
  color: var(--v-dark-base);
 
  &__item:not(:last-child) {
    margin-right: 35px;
  }
}
</style>

<script>
export default {
  name: 'vTabCustom',
  inheritAttrs: false,
  props: {
    name: {type: String, default: undefined}
  },
  methods: {
    onChange(){
      console.log(this.name)
    }
  }
}
</script>
