<script setup>
import '@material/web/checkbox/checkbox.js'
//定义属性接收按钮类型
const props = defineProps({
  label: String,
  disabled: Boolean,
  checked: Boolean
 
})
</script>

<template>
  <div class="default">
    <label>
      <md-checkbox
        touch-target="wrapper"
        :checked="checked"
        :disabled="disabled"
        
      ></md-checkbox>
      {{ label }}
    </label>
  </div>
</template>

<style lang="less" scoped></style>
