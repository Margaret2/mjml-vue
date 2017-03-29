<!-- testing all the components -->
<template>
    <div :style="styles">
      <mj-section full-width="true" background-url="https://images.unsplash.com/photo-1487564149407-9fb3522e2ceb?dpr=1&auto=compress,format&fit=crop&w=600&h=200&q=80&cs=tinysrgb&crop=">
        <h1 style="font-size: 20px;">sljs sl lkjs </h1>
      </mj-section>
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
import mjSection from './mj-section.vue'
import mjText from './mj-text.vue'
export default {
  props: ['background-color', 'width'],
  components: {mjButton, mjDivider, mjImage, mjSection, mjText },
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
