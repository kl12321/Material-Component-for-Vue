<script setup>
import '@material/web/radio/radio.js'
//定义属性接收按钮类型
const props = defineProps({
  name: String,
  value: String,
  label: String,
  checked: Boolean,
  disabled: Boolean,
  change: Function
})
</script>

<template>
  <div class="default">
    <md-radio
      id="radio"
      :name="name"
      :value="value"
      :checked="checked"
      :disabled="disabled"
      @change="change"
    ></md-radio>
    <label for="radio">{{ label }}</label>
  </div>
</template>

<style lang="less" scoped></style>
