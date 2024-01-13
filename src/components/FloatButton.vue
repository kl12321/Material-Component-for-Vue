<script setup>
import '@material/web/fab/branded-fab.js'
import '@material/web/fab/fab.js'
import '@material/web/icon/icon.js'
//定义属性接收按钮类型
const props = defineProps({
  label: String,
  icon: String,
  //small, medium, large
  size: String,
  //是否降低按钮高度，降低后阴影会变小
  lower: Boolean,
  //"surface" (default), "primary", "secondary", or "tertiary"
  variant: String
})
</script>

<template>
  <div class="default">
    <md-fab :label="label" :size="size" :lower="lower" :variant="variant">
      <md-icon slot="icon" >
        <slot></slot>
      </md-icon>
    </md-fab>
  </div>
</template>

<style lang="less" scoped></style>
