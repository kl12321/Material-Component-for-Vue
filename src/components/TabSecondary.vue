<script setup>
import '@material/web/icon/icon.js'
import '@material/web/iconbutton/icon-button.js'
import '@material/web/tabs/primary-tab.js'
import '@material/web/tabs/secondary-tab.js'
import '@material/web/tabs/tabs.js'

//定义属性接收按钮类型
const props = defineProps({
  type: String,
  values: {
    type: Array,
    default: () => []
  },
  autoActivate: Boolean,
  labels: {
    type: Array,
    default: () => []
  },
  active: {
    type: Number,
    default: 0
  },
  iconOnly: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <div class="default">
    <md-tabs :autoActivate="autoActivate" v-if="values.length != 0">
      <template v-for="(value, index) in values" :key="index">
        <md-secondary-tab :active="index == active" :iconOnly="iconOnly">
          <span v-if="!iconOnly">{{ value.label }}</span>
          <md-icon slot="icon">
            <span v-html="value.icon"></span>
          </md-icon>
        </md-secondary-tab>
      </template>
    </md-tabs>

    <md-tabs :autoActivate="autoActivate" v-else>
      <template v-for="(label, index) in labels" :key="index">
        <md-primary-tab
          :inlineIcon="inlineIcon"
          :active="index == active"
          :iconOnly="iconOnly"
        >
          {{ label }}
        </md-primary-tab>
      </template>
    </md-tabs>
  </div>
</template>

<style lang="less" scoped></style>
