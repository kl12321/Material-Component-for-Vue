<script setup>
import '@material/web/select/filled-select.js'
import '@material/web/select/outlined-select.js'
// import '@material/web/select/harness.js'
import '@material/web/select/select-option.js'
//定义属性接收按钮类型
const props = defineProps({
  type: String,
  title: String,
  disabled: Boolean,
  selected: Boolean,
  errorText: String,
  trailingIcon: Boolean,
  supportingText: String,
  required: Boolean,
  value: String,
  change: Function,
  //option
  //item{
  //  label:''
  //  value:''
  //  disabled:false
  //  selected:false
  //  type:''   'option' as const
  //}
  items: {
    type: Array,
    default: () => []
  }
})
</script>

<template>
  <div class="default">
    <md-outlined-select
      v-if="type == 'outlined'"
      :disabled="disabled"
      :required="required"
      :label="title"
      :errorText="errorText"
      :supportingText="supportingText"
      :value="value"
      @change="change"
    >
      <template v-for="(item, index) in items">
        <md-select-option :value="item.value">
          <div slot="headline">{{ item.label }}</div>
        </md-select-option>
      </template>
    </md-outlined-select>

    <md-filled-select v-else>
      <template v-for="(item, index) in items">
        <md-select-option
          :value="item.value"
          :selected="selected"
          :disabled="disabled"
        >
          <div slot="headline">{{ item.label }}</div>
        </md-select-option>
      </template>
    </md-filled-select>
  </div>
</template>

<style scoped>
:root {
  --md-filled-select-text-field-container-shape: 0px;
  --md-filled-select-text-field-container-color: #f7faf9;
  --md-filled-select-text-field-input-text-color: #005353;
  --md-filled-select-text-field-input-text-font: system-ui;
}

md-filled-select::part(menu) {
  --md-menu-container-color: #f4fbfa;
  --md-menu-container-shape: 0px;
}
</style>
