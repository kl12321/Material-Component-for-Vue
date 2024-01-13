<script setup>
import '@material/web/progress/circular-progress.js'
import '@material/web/progress/linear-progress.js'
//定义属性接收按钮类型
const props = defineProps({
  type: String,
  value: Number,
  buffer: Number,
  indeterminate: Boolean,
  fourColor: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <!-- indeterminate与buffer不能同时使用 -->
  <div class="default">
    <md-circular-progress
      v-if="type == 'circular'"
      :value="value"
      :indeterminate="indeterminate"
      :four-color="fourColor"
    ></md-circular-progress>

    <md-linear-progress
      v-if="type == 'linear'"
      :value="value"
      :buffer="buffer"
      :indeterminate="indeterminate"
      :fourColor="fourColor"
    >
    </md-linear-progress>

    <!-- <md-linear-progress value="0.5" buffer="0.8"></md-linear-progress> -->
  </div>
</template>

<style lang="less" scoped></style>
