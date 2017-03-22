<template lang="html">
  <!--[if mso | IE]>
      <table role="presentation" border="0" cellpadding="0" cellspacing="0"><tr><td :height="height || ''" :style="tableStyles">
      <![endif]-->
      <div :style="[styles, {height: height || ''}, customStyles]">
        <slot></slot>
        x y z
      </div>
      <!--[if mso | IE]>
      </td></tr></table>
      <![endif]-->
</template>

<script>
export default {
  props: ['custom-styles', 'height'],
  data: function(){
    return {
      styles: {
        color: '#000000',
        fontFamily: 'Ubuntu, Helvetica, Arial, sans-serif',
        fontSize: '13px',
        lineHeight: '22px',
        textAlign: 'left'
      },
      tableStyles: {
        verticalAlign: 'top',
        height: this.height || ''
      }
    }
  }
}
</script>
