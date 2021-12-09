<template lang="pug">
  .d-flex.flex-column.align-center
    .col-dialog.pb-5
      v-select-custom(:items="items", label="Choose account")
    .col-dialog.pb-9
      v-select-custom(:items="items", label="Choose currency")
    .col-dialog.d-flex.flex-row.justify-center.pb-7
      img.d-block.qr-code(src="@/assets/img.png")
    .col-dialog.text-center.pb-7
      | FGBfvcnkfdnvkk74365832ybvcvdfvfvb
    .col-dialog
      v-btn-custom
        | Copy
</template>

<style scoped lang="scss">
  .qr-code {
    width: 119px;
    height: auto;
  }
</style>

<script>
import VSelectCustom from '@/components/vSelectCustom'
import VBtnCustom from '@/components/vBtnCustom'
export default {
  name: 'deposit',
  components: { VBtnCustom, VSelectCustom },
  data () {
    return {
      items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    }
  }
}
</script>
