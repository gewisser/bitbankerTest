<template lang="pug">
  .d-flex.flex-column.align-center
    .col-dialog.pb-5
      v-select-custom(:items="items", label="Choose exchange")
    .col-dialog.pb-5
      v-select-custom(:items="items", label="Choose currency")
    .col-dialog.pb-9
      v-select-custom(:items="items", label="Withdraw amount")
        template(v-slot:append)
          v-btn.max-btn(color="label", depressed)
            | Max
    .col-dialog
      v-btn-custom
        | Withdraw
</template>

<style scoped lang="scss">
  .max-btn {
    color: var(--v-white-base);
  }
</style>

<script>
import VSelectCustom from '@/components/vSelectCustom'
import VBtnCustom from '@/components/vBtnCustom'

export default {
  name: 'withdraw',
  components: { VBtnCustom, VSelectCustom },
  data () {
    return {
      items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    }
  }
}
</script>
