<template lang="html">
  <!--[if mso | IE]>
   <table role="presentation" border="0" cellpadding="0" cellspacing="0" align="center" width="100%" style="width:100%;">
     <tr>
       <td style="padding:0;background-color:transparent;">
  <![endif]-->
  <div class="mj-hero-content" :style="[divStyle, customStyles]">
       <table role="presentation" cellpadding="0" cellspacing="0" style="width:100%;margin:0px;">
         <tbody>
           <tr>
             <td :style="tdStyle">
               <table role="presentation" style="width:100%;margin:0px;">
                 <tbody>
                     <slot></slot>
                 </tbody>
               </table>
             </td>
           </tr>
         </tbody>
       </table>
     </div>
  <!--[if mso | IE]>
       </td>
     </tr>
   </table>
<![endif]-->
</template>

<script>
export default {
  props: ['background-color', 'custom-styles', 'padding' ],
  data: function(){
    return {
      divStyle: {
        float: 'center',
        margin: '0px auto',
        width: '100%',
        backgroundColor: this.backgroundColor || 'transparent'
      },
      tdStyle: {
        padding: this.padding || '0px'
      }
    }
  }
}
</script>

<style lang="css">
    @media only screen and (max-width:480px) {
      .mj-hero-content {
        width: 100% !important;
      }
    }
</style>
