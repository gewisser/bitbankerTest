<template lang="pug">
  .d-flex.flex-column.align-center
    .col-dialog.pb-5
      v-select-custom(:items="items", label="Choose exchange", outside-label="From")
    .col-dialog.pb-5
      v-select-custom(:items="items", label="Choose exchange", outside-label="To")
    .col-dialog.pb-5
      v-select-custom(:items="items", label="Choose currency")
    .col-dialog.pb-1
      v-text-field-custom(v-model="amount", :show-popup-menu.sync="showTextFieldPopup")
        template(v-slot:popup)
          .d-flex.flex-row.flex-wrap.popup-container
            .d-flex.flex-column.balance-label.justify-center.align-center.px-2
              div
                | Balance:
                |
                b 0.04763864
            .break
            v-btn.btn-preselector-percent(color="label", depressed, min-width="45")
              | 10%
            v-btn.btn-preselector-percent(color="label", depressed, min-width="45")
              | 25%
            v-btn.btn-preselector-percent(color="label", depressed, min-width="45")
              | 50%
            v-btn.btn-preselector-percent(color="label", depressed, min-width="45")
              | 100%
            v-btn.btn-preselector-percent(color="label", depressed, min-width="45")
              | Split

    .col-dialog.pb-5
      v-checkbox(label="Instant rebalance", on-icon="$checkboxChecked", off-icon="$checkboxUnChecked")
    .col-dialog
      v-btn-custom
        | Apply
</template>

<style scoped lang="scss">
  .v-btn.btn-preselector-percent {
    color: var(--v-white-base);
    font-weight: bold;
    font-size: 12px;
    line-height: 16px;
    padding: 0 12px;
    margin-right: 10px;
  }

  .balance-label {
    height: 32px;
    background: rgba(42, 101, 145, 0.1);
    border-radius: 3px;
    color: var(--v-primary-base);
    font-size: 12px;
    line-height: 16px;
    margin-bottom: 10px;
  }

  .break {
    flex-basis: 100%;
    height: 0;
  }
</style>

<script>
import VSelectCustom from '@/components/vSelectCustom'
import VTextFieldCustom from '@/components/vTextFieldCustom'
import VBtnCustom from '@/components/vBtnCustom'

export default {
  name: 'Rebalance',
  components: { VTextFieldCustom, VSelectCustom, VBtnCustom },
  data () {
    return {
      items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
      showTextFieldPopup: false,
      amount: undefined
    }
  },
  
  watch: {
    amount(val){
      this.showTextFieldPopup = val == 2
    }
  }
}
</script>
