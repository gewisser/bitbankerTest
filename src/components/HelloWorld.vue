<template lang="pug">
  v-dialog(v-model="showDialog", persistent, max-width="780", content-class="custom-dialog", overlay-color="transparent")
    v-icon.close-icon(@click="showDialog = false")
      | $close
    v-tabs-custom.pb-10(v-model="tabPage")
      v-tab-custom(v-for="tab in tabPages", :key="tab") {{ tab }}
    component(:is="tabPages[tabPage]")
</template>

<style lang="scss">
  .v-dialog.custom-dialog {
    background: var(--v-white-base);
    padding: 10px 30px 71px 30px;
    box-shadow: unset;
    position: relative;
    
    .close-icon {
      position: absolute;
      width: auto;
      z-index: 1;
      right: 29px;
      top: 28px;
      cursor: pointer;
    }
  
    .col-dialog {
      max-width: 380px;
      width: 100%;
    }
  }
</style>

<script>
  import VTabCustom from '@/components/vTabCustom'
  import VTabsCustom from '@/components/vTabsCustom'
  
  export default {
    name: 'HelloWorld',
    components: {
      VTabsCustom,
      VTabCustom,
      Deposit: () =>  import("@/components/tabs/deposit"),
      Withdraw: () =>  import("@/components/tabs/withdraw"),
      Rebalance: () =>  import("@/components/tabs/rebalance"),
    },
    data(){
      return {
        showDialog: true,
        tabPage: 0,
        tabPages: ["Deposit", "Withdraw", "Rebalance"]
      }
    }
  }
</script>
