<template lang="html">
  <tr>
  <td :style="tdStyle" align="center">
    <table role="presentation" cellpadding="0" cellspacing="0" :style="tableStyle" align="center" border="0">
      <tbody>
        <tr>
          <td :style="{width: contentWidth}">
            <img alt="" title="" height="auto"
                      :src="src || '#'"
                      :style="imgStyle" :width="parseInt(contentWidth)">
            </td>
        </tr>
      </tbody>
    </table>
  </td>
</tr>
</template>

<script>
export default {
  props: ['src', 'padding', 'full-width', 'content-width'],
  data: function(){
    return {
      tdStyle: {
        fontSize: '0px',
        padding: this.padding || '10px 25px 10px 25px',
        wordBreak: 'break-word'
      },
      tableStyle: {
        borderCollapse: 'collapse',
        borderSpacing: '0px'
      },
      imgStyle: {
        border: 'none',
        display: 'block',
        height: 'auto',
        outline: 'none',
        textDecoration: 'none',
        width: '100%'
      }
    }
  }
}
</script>
<!--
- parent width = attr width
- "width" = parent width or img width
- overflow = diff between parent width and padding + "width" - parent width // 100px vs. 30 + 50 + 30, overflow is 10, result is 40
-->
