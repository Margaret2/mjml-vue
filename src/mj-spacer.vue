<template lang="html">
  <tr>
  <td :style="tdStyle">
    <div :style="divStyle">&nbsp;</div>
  </td>
</tr>
</template>

<script>
export default {
  props: ['height'],
  data: function(){
    return {
      tdStyle: {
        wordBreak: 'break-word',
        fontSize: '0px'
      },
      divStyle: {
        fontSize: '1px',
        lineHeight: this.height || 0,
        whiteSpace: 'nowrap'
      }
    }
  }
}
</script>

<style lang="css">
</style>
