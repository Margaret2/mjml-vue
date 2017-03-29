<!--TODO: get width -->
<template lang="html">
  <!--[if mso | IE]>
  <table role="presentation" border="0" cellpadding="0" cellspacing="0" :width="parseFloat(width) || 600" align="center" :style="{width: width || '600px'}">
    <tr>
      <td style="line-height:0px;font-size:0px;mso-line-height-rule:exactly;">
  <![endif]-->
<div v-if="backgroundUrl" :style="divStyle">
  <!--[if mso | IE]>
    <v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" :style="{width: width || '600px'}">
        <v:fill origin="0.5, 0" position="0.5,0" type="tile" :src="backgroundUrl" />
        <v:textbox style="mso-fit-shape-to-text:true" inset="0,0,0,0">
    <![endif]-->
  <table role="presentation" cellpadding="0" cellspacing="0" :style="tableStyle" align="center" border="0">
    <tbody>
      <tr>
        <td :style="tdStyle">
          <slot></slot>
        </td>
      </tr>
</tbody>
</table>
<!--[if mso | IE]>
  </v:textbox>
</v:rect>
<![endif]-->
</div>
<div v-else :style="divStyle">
  <table role="presentation" cellpadding="0" cellspacing="0" :style="tableStyle" align="center" border="0">
    <tbody>
      <tr>
        <td :style="tdStyle">
          <slot></slot>
        </td>
      </tr>
</tbody>
</table>
</div>
<!--[if mso | IE]>
</td></tr></table>
<![endif]-->
</template>

<script>
export default {
  props:['background-url', 'full-width', 'width'],
  data: function(){
    return {
      divStyle: {
        margin: '0px auto',
        maxWidth: this.fullWidth ? '' : this.width ? this.width : '600px',
        background:  `url(${this.backgroundUrl}) top center / auto repeat`
      },
      tableStyle: {
        fontSize: '0px',
        width: '100%'
      },
      tdStyle: {
        textAlign: 'center',
        verticalAlign: 'top',
        fontSize: '0px',
        padding: '0px 20px'
      }
    }
  }
}
</script>
