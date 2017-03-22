<template lang="html">
    <div :style="[styles, customStyles]">
      <slot></slot>
    </div>
</template>

<script>
export default {
  props: ['custom-styles'],
  data: function(){
    return {
      styles: {
        fontSize: '13px'
      }
    }
  }
}
</script>
