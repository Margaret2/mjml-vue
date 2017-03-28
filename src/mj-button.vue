<template lang="html">
  <table :align="align || 'center'" border="0" cellpadding="0" cellspacing="0" role="presentation" :style="[styles.table, customStyles]">
      <tr>
          <td align="center" :bgcolor="backgroundColor || '#414141'" :style="[styles.td, customStyles]" :valign="verticalAlign ||'middle' ">
              <a v-if="href" :href="href" :style="" target="_blank" :style="[styles.a, customStyles]">
                <slot></slot>
              </a>
              <p v-else :style="[styles.p, customStyles]">
                <slot></slot>
              </p>
          </td>
      </tr>
  </table>
</template>

<script>
export default {
  props: ['align', 'background-color', 'custom-styles', 'href', 'verticalAlign'],
  data: function(){
    return {
      styles: {
        a: {
          background: '#414141',
          color: '#ffffff',
          fontFamily: 'Ubuntu, Helvetica, Arial, sans-serif',
          fontSize: '13px',
          fontWeight: 'normal',
          lineHeight: '100%',
          margin: '0px',
          textDecoration: 'none',
          textTransform: 'none'
        },
        p: {
          background: '#414141',
          color: '#ffffff',
          fontFamily: 'Ubuntu, Helvetica, Arial, sans-serif',
          fontSize: '13px',
          fontWeight: 'normal',
          lineHeight: '100%',
          margin: '0px',
          textDecoration: 'none',
          textTransform: 'none'
        },
        table: {
          borderCollapse: 'separate'
        },
        td: {
          border: 'none',
          borderRadius: '3px',
          color: '#ffffff',
          cursor: 'auto',
          padding: '10px 25px'
        }
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
