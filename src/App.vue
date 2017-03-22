<!-- testing all the components -->
<template>
  <div>
      <mj-button href="google.com">Click me</mj-button>
      <!--temporary table so the divider will work-->
      <table><tbody>
      <mj-divider></mj-divider>
    </tbody></table>
      <mj-image src="#" width="100px"></mj-image>
      <mj-html>13px div content</mj-html>
      <mj-text height="250px"></mj-text>
  </div>
</template>

<script>
import mjButton from './mj-button.vue'
import mjDivider from './mj-divider.vue'
import mjHtml from './mj-html.vue'
import mjImage from './mj-image.vue'
import mjText from './mj-text.vue'
export default {
  components: { mjButton, mjDivider, mjImage, mjHtml, mjText }
}
</script>

<style>

</style>
