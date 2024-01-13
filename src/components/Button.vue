<script setup>
import '@material/web/button/elevated-button.js'
import '@material/web/button/filled-button.js'
import '@material/web/button/filled-tonal-button.js'
import '@material/web/button/outlined-button.js'
import '@material/web/button/text-button.js'
import '@material/web/icon/icon.js'
//定义属性接收按钮类型
const props = defineProps({
  type: String,
  label: String,
  icon: String,
  disabled: Boolean,
  trailingIcon: Boolean
})
</script>

<template>
  <div class="default">
    <!-- 边线按钮 -->
    <md-outlined-button v-if="type == 'outlined'">
      {{ label }}
      <slot>
        <!-- icon   -->
      </slot>
    </md-outlined-button>
    <!-- 填充按钮 -->
    <md-filled-button v-if="type == 'filled'">
      {{ label }}
      <slot>
        <!-- icon   -->
      </slot>
    </md-filled-button>
    <!-- 突起按钮 -->
    <md-elevated-button v-if="type == 'elevated'">
      {{ label }}
      <slot>
        <!-- icon   -->
      </slot>
    </md-elevated-button>
    <!-- ···填充色调按钮··· -->
    <md-filled-tonal-button v-if="type == 'filled-tonal'">
      {{ label }}
      <slot>
        <!-- icon   -->
      </slot>
    </md-filled-tonal-button>
    <!-- 文本按钮 -->
    <md-text-button v-if="type == 'text'">
      {{ label }}
      <slot>
        <!-- icon   -->
      </slot>
    </md-text-button>
  </div>
</template>

<style lang="less" scoped></style>
