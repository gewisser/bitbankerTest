<template lang="pug">
  v-btn(v-bind='$attrs', v-on='$listeners', depressed, color="primary", width="100%", height="50")
    template(v-for="slot in Object.keys($scopedSlots)", v-slot:[slot])
      slot(:name="slot")
</template>

<script>
export default {
  name: 'vBtnCustom',
  inheritAttrs: false,
}
</script>
