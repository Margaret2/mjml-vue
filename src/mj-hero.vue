<template lang="html">
  <!--[if mso | IE]>
  <table role="presentation" border="0" cellpadding="0" cellspacing="0" :width="getWidth" align="center" :style="{width: getWidth + 'px'}">
    <tr>
      <td style="line-height: 0px; font-size: 0px; mso-line-height-rule: exactly">
  <![endif]-->
<!--[if mso | IE]>
      <v:image xmlns:v="urn:schemas-microsoft-com:vml" :croptop="getCrop[0]" :cropbottom="getCrop[1]" :style="vStyle" :src="src" />
    <![endif]-->
    <div :style="{margin: '0 auto', maxWidth: this.getWidth + 'px' || '600px'}">
   <table role="presentation" cellpadding="0" cellspacing="0" style="width:100%;">
     <tbody>
       <tr v-if="fixedHeight" style="vertical-align: top;">
          <td :background="src"></td>
       </tr>

       <tr v-else style="vertical-align:top;">
         <td style="padding-bottom:78.1667%;width:0.01%;mso-padding-bottom-alt:0;"></td>
         <td :style="[tdStyle, customStyles]" :background="src">
              <slot></slot>
         </td>
         <td style="padding-bottom:78.1667%;width:0.01%;mso-padding-bottom-alt:0;"></td>
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
  // bg-height, bg-width, img-height, and img-width required only if mode is "fixed"
  props: ['custom-styles', 'full-width', 'mode', 'src',
                'bg-height', 'bg-position', 'bg-width', 'img-height', 'img-width'],
  data: function(){
    return {
      getWidth: parseInt(this.fullWidth) ||  600,
      fixedHeight: this.mode === "fixed" ? true : false,
      tdStyle: {
        backgroundRepeat: 'no-repeat',
        verticalAlign: 'top',
        backgroundSize: 'cover',
        background: `url(${this.src || '#'}) no-repeat center center / cover`,
        padding: '0px',
        backgroundPosition: 'center center'
      },
      vStyle: {
        width: this.bgWidth ? parseInt(this.bgWidth)*0.75 + 'pt' : '0pt',
        height: this.bgHeight ? parseInt(this.bgHeight)*0.75 + 'pt' : '0pt',
        position: 'absolute',
        top: 0,
        msoPositionHorizontal: 'center',
        border: 0,
        zIndex: -3
      }
    }
  },
  computed: {
    getCrop: function(){
      let h = parseInt(this.imgHeight)
      let bgh = parseInt(this.bgHeight)
      let bgp = this.bgPosition || "center"
      let arr = [0, 0]
      if (h < bgh) {
        switch(bgp){
          case "top":
            arr[1] = Math.round((bgh - h) / bgh * 100) / 100;
            break;
          case "center":
            arr[0] = Math.round((bgh - h) / 2 / bgh * 100) / 100;
            arr[1] = arr[0];
            break;
          case "bottom":
            arr[0] = Math.round((bgh - h) / bgh * 100) / 100;
            break;
        }
      }
      return arr;
    }
  }
}
</script>

<style lang="css">
</style>
