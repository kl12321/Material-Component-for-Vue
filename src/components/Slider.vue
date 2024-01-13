<script setup>
import '@material/web/slider/slider.js'
const labels = ['🤬', '😡', '😔', '😐', '😌', '😁', '🤪']
//定义属性接收按钮类型
const props = defineProps({
  max: {
    type: Number,
    default: 100
  },
  min: {
    type: Number,
    default: 0
  },
  step: {
    type: Number,
    default: 1
  },
  value: {
    type: Number,
    default: 0
  },
  ticks: {
    type: Boolean,
    default: false
  },
  range: {
    type: Boolean,
    default: false
  },
  valueStart: {
    //range为true时，valueStart和valueEnd才有用，valueStart和valueEnd为初始值
    type: Number,
    default: 0
  },
  valueEnd: {
    type: Number,
    default: 0
  },
  valueLabelStart: {
    //自定义初始值的标签
    type: String,
    default: ''
  },
  valueLabelEnd: {
    //自定义初始值的标签
    type: String,
    default: ''
  },
  valueLabel: {
    //当 range 为 false 时,标签显示的内容
    type: String,
    default: ''
  },

  labeled: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <div class="default">
    <md-slider
      :ticks="ticks"
      :value="value"
      :min="min"
      :max="max"
      :step="step"
      :range="range"
      :value-start="valueStart"
      :value-end="valueEnd"
      :value-label="valueLabel"
      :value-label-start="valueLabelStart"
      :value-label-end="valueLabelEnd"
      :labeled="labeled"
    ></md-slider>
  </div>
</template>

<style lang="less" scoped></style>
