<template lang="html">
  <table :align="align || 'center'" :border="border || 0" cellpadding="0" cellspacing="0" role="presentation" :style="[styles.table, customStyles]">
    <tbody>
      <tr>
        <td :style="[{width: width || ''}, customStyles]">
          <a v-if="href" :href="href || ''" :target="target || '_blank'">
            <img :alt="alt || ''" :src="src || ''" :height="height || 'auto'" :style="[styles.img, customStyles]" :title="title || ''" :width="width || ''">
          </a>
          <img :alt="alt || ''" :src="src || ''" :height="height || 'auto'" :style="[styles.img, customStyles]" :title="title || ''" :width="width || ''">
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: ['align', 'alt', 'border', 'border-radius','custom-styles', 'height', 'href', 'padding-arr','src', 'target', 'title', 'width'],
  data: function(){
    return {
      styles: {
        table: {
          borderCollapse: 'collapse',
          borderSpacing: '0px'
        },
        img: {
          border: 'none',
          borderRadius: '',
          height: 'auto',
          display: 'block',
          outline: 'none',
          textDecoration: 'none',
          width: '100%'
        }
      }
    }
  },
  computed: {
    getComputedWidth: function(){
        // return width TODO
    }
  }
}
</script>

<style lang="css">
</style>
<!--
            <table role="presentation" cellpadding="0" cellspacing="0" style="border-collapse:collapse;border-spacing:0px;" align="center" border="0">
              <tbody>
                  <tr>
                    <td style="width:100px;">
                      <img alt="" title="" height="auto" src="/assets/img/logo-small.png"
                      style="border:none;border-radius:;display:block;outline:none;text-decoration:none;width:100%;height:auto;"
                      width="100">
                  </td>
                      </tr>
               </tbody>
             </table>
-->
