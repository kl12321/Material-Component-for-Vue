<script setup>
import '@material/web/chips/assist-chip.js'
import '@material/web/chips/chip-set.js'
import '@material/web/chips/filter-chip.js'
import '@material/web/chips/input-chip.js'
import '@material/web/chips/suggestion-chip.js'
//定义属性接收按钮类型
const props = defineProps({
  //value:{
  //  type:assist||filter||input||suggestion,
  //  label:label,
  //  disabled:true||false,
  //  elevated:true||false,
  //  target:_self||_blank, (assist)
  //  href:link,(assist),
  //  removable:true||false (filter)
  //  selected:true||false (filter)
  //  handleTrailingActionFocus:()=>{},(filter,input) //点击删除按钮时触发
  //  icon:svg标签的字符串 //图标
  //  avatar:boolean //是否显示头像

  //}
  values: {
    type: Array,
    default: () => []
  }
})
</script>

<template>
  <div class="default">
    <md-chip-set>
      <template v-for="(item, index) in values" :key="index">
        <template v-if="item.type === 'assist'">
          <md-assist-chip
            :label="item.value"
            :disabled="item.disabled"
            :elevated="item.elevated"
            :href="item.href"
            :target="item.target"
          >
            <md-icon slot="icon">
              <md-icon slot="icon"> <span v-html="item.icon"></span> </md-icon>
            </md-icon>
          </md-assist-chip>
        </template>
        <template v-if="item.type === 'filter'">
          <md-filter-chip
            :label="item.value"
            :disabled="item.disabled"
            :elevated="item.elevated"
            :removable="item.removable"
            :selected="item.selected"
            :handleTrailingActionFocus="item.handleTrailingActionFocus"
          >
            <md-icon slot="icon" v-html="item.icon">
              
            </md-icon>
          </md-filter-chip>
        </template>
        <template v-if="item.type === 'input'">
          <md-input-chip
            :label="item.value"
            :disabled="item.disabled"
            :elevated="item.elevated"
            :avatar="item.avatar"
            :handleTrailingActionFocus="item.handleTrailingActionFocus"
          >
            <md-icon slot="icon">
              <span v-html="item.icon"></span>
            </md-icon>
          </md-input-chip>
        </template>
        <template v-if="item.type === 'suggestion'">
          <md-suggestion-chip
            :label="item.value"
            :disabled="item.disabled"
            :elevated="item.elevated"
          >
            <md-icon slot="icon">
              <span v-html="item.icon"></span>
            </md-icon>
          </md-suggestion-chip>
        </template>
      </template>
    </md-chip-set>
  </div>
</template>

<style lang="less" scoped></style>
