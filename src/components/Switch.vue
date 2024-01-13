<script setup>
import '@material/web/switch/switch.js'
//定义属性接收按钮类型
const props = defineProps({
  selected: Boolean,
  disabled: Boolean,
  label: {
    type: String,
    default: ''
  },
  required: Boolean,
  icons: Boolean,
  checked: Boolean,
  value: Boolean,
  onChange: Function,
  onInput: Function
})
</script>

<template>
  <div class="default">
    <md-switch
      id="switch"
      :selected="selected"
      :disabled="disabled"
      :required="required"
      :value="value"
      :icons="icons"
      @change="onChange"
      @input="onInput"
    ></md-switch>

    <label v-if="label != ''" for="switch">{{ label }}</label>
  </div>
</template>

<style lang="less" scoped></style>
