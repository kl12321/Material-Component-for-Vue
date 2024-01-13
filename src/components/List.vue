<script setup>
import '@material/web/list/list.js'
import '@material/web/list/list-item.js'
import '@material/web/divider/divider.js'
import '@material/web/icon/icon.js'
//定义属性接收按钮类型
const props = defineProps({
  divider: Boolean,
  maxWidth: String, //最大宽度,px
  interactive: Boolean, //是否可交互
  //列表数据
  //{
  //  content: 'content',
  //  headline: 'headline',
  //  supportingText: 'supportingText'
  //  href: String, //链接
  //  target: String, //链接打开方式
  //  startIcon: String, //开始图标
  //  startImage: String, //开始图片
  //  endIcon: String, //结束图标
  //  endImage: String //结束图片
  // trailingSupportingText: String //尾部支持文本
  // type: String //类型,Sets the behavior of the list item, defaults to "text". Change to "link" or "button" for interactive items.
  //}
  list: {
    type: Array,
    default: () => []
  }
})
</script>

<template>
  <div class="default">
    <md-list>
      <template v-for="(item, index) in list">
        <md-list-item
          :href="item.href"
          :target="item.target"
          :interactive="interactive"
        >
          <span slot="start" v-html="item.startIcon"> </span>
          <img slot="start" :src="item.startImage" alt="" />
          {{ item.content }}
          <div slot="headline" v-if="item.headline != ''">
            {{ item.headline }}
          </div>
          <div slot="supporting-text" v-if="item.supportingText != ''">
            {{ item.supportingText }}
          </div>
          <div slot="trailing-supporting-text">
            {{ item.trailingSupportingText }}
          </div>
          <span slot="end" v-html="item.endIcon"> </span>
          <img slot="end" :src="item.endImage" alt="" />
        </md-list-item>

        <md-divider v-if="divider"></md-divider>
      </template>
    </md-list>
  </div>
</template>

<style lang="less" scoped></style>
