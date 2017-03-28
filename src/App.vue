<!-- testing all the components -->
<template>
    <div :style="styles">
      <mj-button href="google.com">Click me</mj-button>
      <!--temporary table so the divider will work-->
      <table><tbody>
      <mj-divider></mj-divider>
    </tbody></table>
      <mj-image src="#" width="100px"></mj-image>
      <mj-text height="250px"></mj-text>
    </div>
</template>

<script>
import mjButton from './mj-button.vue'
import mjDivider from './mj-divider.vue'
import mjImage from './mj-image.vue'
import mjText from './mj-text.vue'
export default {
  props: ['background-color', 'width'],
  components: {mjButton, mjDivider, mjImage, mjText },
  data: function(){
    return {
      styles: {
        backgroundColor: this.backgroundColor,
        width: this.width || '600px'
      }
    }
  }
}
</script>

<style>

</style>
