<script setup>
import '@material/web/iconbutton/filled-icon-button.js'
import '@material/web/iconbutton/filled-tonal-icon-button.js'
import '@material/web/iconbutton/icon-button.js'
import '@material/web/iconbutton/outlined-icon-button.js'

//定义属性接收按钮类型
const props = defineProps({
  type: String,
  selected: Boolean,
  disabled: Boolean,
  checked: Boolean,
  href: String,
  target: String,
  toggle: Boolean,
  value: String
})
</script>

<template>
  <div class="default">
    <md-icon-button
      v-if="type == 'ordinary'"
      :href="href"
      :target="target"
      :toggle="toggle"
      :value="value"
      :selected="selected"
      :disabled="disabled"
    >
      <md-icon>
        <slot></slot>
      </md-icon>
      <md-icon slot="selected">
        <slot name="selected"></slot>
      </md-icon>
    </md-icon-button>

    <md-filled-icon-button
      v-else-if="type == 'filled'"
      :href="href"
      :target="target"
      :toggle="toggle"
      :value="value"
      :selected="selected"
      :disabled="disabled"
    >
      <md-icon>
        <slot></slot>
      </md-icon>
      <md-icon slot="selected">
        <slot name="selected"></slot>
      </md-icon>
    </md-filled-icon-button>

    <md-filled-tonal-icon-button
      v-else-if="type == 'filledTonal'"
      :href="href"
      :target="target"
      :toggle="toggle"
      :value="value"
      :selected="selected"
      :disabled="disabled"
    >
      <md-icon>
        <slot></slot>
      </md-icon>
      <md-icon slot="selected">
        <slot name="selected"></slot>
      </md-icon>
    </md-filled-tonal-icon-button>

    <md-outlined-icon-button
      v-else
      :href="href"
      :target="target"
      :toggle="toggle"
      :value="value"
      :selected="selected"
      :disabled="disabled"
    >
      <md-icon>
        <slot></slot>
      </md-icon>
      <md-icon slot="selected">
        <slot name="selected"></slot>
      </md-icon>
    </md-outlined-icon-button>
  </div>
</template>

<style lang="less" scoped></style>
