<template lang="pug">
  .d-flex.flex-column.align-center.justify-center
    template(v-if="name === 'arrow-down'")
      svg.d-block(width='10' height='7' viewBox='0 0 10 7' fill='none' xmlns='http://www.w3.org/2000/svg')
        path(d='M1 1.39941L4.8995 5.29891L8.79899 1.39941' stroke='#9AA2A8' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
    template(v-else-if="name === 'close-icon'")
      svg(width='22' height='23' viewBox='0 0 22 23' fill='none' xmlns='http://www.w3.org/2000/svg')
        path(d='M1 1.5L21 21.5' stroke='#9AA2A8' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
        path(d='M21 1.5L0.999999 21.5' stroke='#9AA2A8' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
    template(v-else-if="name === 'checkbox-checked'")
      svg(width='20' height='21' viewBox='0 0 20 21' fill='none' xmlns='http://www.w3.org/2000/svg')
        rect(y='0.5' width='20' height='20' rx='5' fill='#3C484C')
        path(d='M5 10.5713L9.04061 14.6119L16.1117 7.54083' stroke='white' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round')
    template(v-else-if="name === 'checkbox-unchecked'")
      svg(width='20' height='21' viewBox='0 0 20 21' fill='none' xmlns='http://www.w3.org/2000/svg')
        rect(y='0.5' width='20' height='20' rx='5' fill='#3C484C')
     
</template>

<style scoped lang="scss">
</style>

<script>
export default {
  name: 'iconSet',
  props: {
    name: {type: String, default: ''}
  }
}
</script>
