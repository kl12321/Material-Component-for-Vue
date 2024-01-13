<script setup>
import '@material/web/divider/divider.js'
import '@material/web/icon/icon.js'
import '@material/web/menu/menu.js'
import '@material/web/menu/menu-item.js'
import '@material/web/menu/sub-menu.js'
import { ref } from 'vue'
import { defineEmits } from 'vue'
//定义属性接受按钮类型
const props = defineProps({
  anchor: String,
  //锚点位置
  anchorCorner: String,
  //菜单角落位置
  menuCorner: String,
  //菜单项
  //{
  //   {
  //     content: 'content',
  //     icon: 'icon',
  //     subMenu: [
  //       {
  //         content: 'content',
  //         icon: 'icon',
  //         subMenu: [
  //           {
  //             content: 'content',
  //             icon: 'icon',
  //             }
  //         ]
  //    }
  //]

  //   }
  //}
  items: {
    type: Array,
    default: () => []
  }
})
const menu = ref(null)
const open = () => {
  menu.value.open = !menu.value.open
}
const emit = defineEmits(['submit'])
const submit = (content) => {
  emit('submit', content)
}
defineExpose({ open })
</script>

<template>
  <md-menu
    id="usage-menu"
    :anchor="anchor"
    ref="menu"
    has-overflow
    :anchorCorner="anchorCorner"
    :menuCorner="menuCorner"
  >
    <template v-for="item in items">
      <md-sub-menu menu-corner="start-start" anchor-corner="start-end">
        <md-menu-item slot="item" @click="submit(item.content)">
          <div slot="headline">{{ item.content }}</div>
          <!-- Arrow icons are helpful affordances -->
          <span slot="start" v-html="item.icon"> </span>
        </md-menu-item>
        <md-menu slot="menu">
          <md-menu-item
            v-for="subItem in item.subMenu"
            @click="submit(subItem.content)"
          >
            <div slot="headline">{{ subItem.content }}</div>
            <!-- Arrow icons are helpful affordances -->
            <span slot="start" v-html="subItem.icon"> </span>
          </md-menu-item>
        </md-menu>
      </md-sub-menu>
    </template>
  </md-menu>
</template>

<style lang="less" scoped></style>
