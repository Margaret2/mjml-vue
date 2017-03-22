<template lang="html">
  <tr>
    <td :style="styles.td">
      <p :style="[styles.p, {borderTop: `
          ${borderWidth || '4px'}
          ${borderStyle || 'solid'}
          ${borderColor || '#000000'}
          `, width: '100%' }, customStyles]"></p>
          <!--[if mso | IE]>
            <table role="presentation" align="center" border="0" cellpadding="0" cellspacing="0"
            :style="[styles.p, {borderTop: `
               ${borderWidth || '4px'}
               ${borderStyle || 'solid'}
               ${borderColor || '#000000'}
               `, width: '100%' }, customStyles]" width="getComputedWidth">
                 <tr><td style="height:0;line-height:0;">&nbsp;</td></tr>
            </table>
          <![endif]-->
      </td>
    </tr>
</template>

<script>
export default {
  props: ['border-color', 'border-style', 'border-width', 'custom-styles', 'width'],
  data: function(){
    return {
      styles: {
        p: {
          fontSize: '1px',
          margin: '0px auto'
        },
        td: {
          wordBreak:'break-word',
          fontSize: '0px',
          padding: '10px 25px'
        }
      }
    }
  },
  methods: {
    getComputedWidth: function(){
      // TODO: get parent width (this.$parent)
    }
  }
}
</script>
