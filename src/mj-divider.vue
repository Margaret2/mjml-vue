<template lang="html">
  <tr>
    <td :style="styles.td">
      <p :style="[styles.p, customStyles]"></p>
          <!--[if mso | IE]>
            <table role="presentation" align="center" border="0" cellpadding="0" cellspacing="0"
            :style="[{width: '100%'}, customStyles]" :width="computedWidth">
                 <tr><td style="height:0;line-height:0;">&nbsp;</td></tr>
            </table>
          <![endif]-->
      </td>
    </tr>
</template>

<script>
export default {
  props: ['custom-styles', 'full-width', 'content-width'],
  data: function(){
    return {
      styles: {
        p: {
          fontSize: '1px',
          margin: '0px auto',
          border: '4px solid #000000',
          width: this.contentWidth || '100%'
        },
        td: {
          wordBreak:'break-word',
          fontSize: '0px',
          padding: '10px 25px'
        }
      }
    }
  },
  computed: {
    computedWidth: function(){
      let x = this.contentWidth
      let y = parseFloat(this.contentWidth)
      let z = parseFloat(this.fullWidth)
      return x.slice(-2) === "px" ? z - y : z * (y/100)
    }
  }
}
</script>
