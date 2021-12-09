<template lang="pug">
  div
    v-menu(:value="showPopupMenu", content-class="custom-menu", @input="onShowMenu", offset-y)
      template(v-slot:activator="{ on, attrs }")
        v-text-field(v-bind='$attrs', v-on='$listeners', solo, flat, background-color="border", height="52", hide-details)
          template(v-for="slot in Object.keys($scopedSlots)", v-slot:[slot])
            slot(:name="slot")
      slot(name="popup")
</template>

<style lang="scss">
  .custom-menu {
    padding: 20px;
    background: var(--v-white-base);
    max-width: 380px;
  }
</style>

<script>
export default {
  name: 'vTextFieldCustom',
  inheritAttrs: false,
  props: {
    showPopupMenu: {type: Boolean, default: false}
  },
  
  methods: {
    onShowMenu(val){
      this.$emit("update:showPopupMenu", val)
    }
  }
}
</script>
