<script setup>
import '@material/web/textfield/filled-text-field.js'
import '@material/web/textfield/outlined-text-field.js'
import '@material/web/textfield/filled-text-field.js'
import { onMounted, ref, defineExpose } from 'vue'
//定义属性接收按钮类型
const props = defineProps({
  type: String,
  placeholder: {
    type: String,
    default: ''
  },
  ariaLabel: {
    type: String,
    default: ''
  },
  disabled: Boolean,
  required: Boolean,
  value: {
    type: String,
    default: ''
  },
  //format为textarea时，为多行文本
  format: String,
  error: Boolean,
  errorText: String,
  label: String,
  prefixText: String,
  suffixText: String,
  supportingText: String,
  inputMode: String,
  max: String,
  maxLength: Number,
  min: String,
  minLength: Number,
  rows: String,
  pattern: String,
  readOnly: Boolean,
  multiple: Boolean,
  step: String,
  autocomplete: String
})
let checkValidity=ref(null)
let reportValidity=ref(null)
let setCustomValidity=ref(null)
const input = ref(null)
onMounted(() => {
  console.log(input.value.checkValidity());
  checkValidity.value = input.value.checkValidity
  reportValidity.value = input.value.reportValidity
  setCustomValidity.value = input.value.setCustomValidity
})

defineExpose({ checkValidity, reportValidity, setCustomValidity })
</script>

<template>
  <div class="default">
    <md-filled-text-field
      ref="input"
      v-if="type === 'filled'"
      :rows="rows"
      :label="label"
      :value="value"
      :type="format"
      :placeholder="placeholder"
      :error="error"
      :error-text="errorText"
      :prefix-text="prefixText"
      :suffix-text="suffixText"
      :supporting-text="supportingText"
      :maxlength="maxLength"
      :minLength="minLength"
      :pattern="pattern"
      :max="max"
      :min="min"
      :step="step"
    >
      <slot slot="leading-icon"></slot>
    </md-filled-text-field>

    <md-outlined-text-field
      v-else
      ref="input"
      :label="label"
      :value="value"
      :required="required"
      :type="format"
      :placeholder="placeholder"
      :error="error"
      :error-text="errorText"
      :prefix-text="prefixText"
      :suffix-text="suffixText"
      :supporting-text="supportingText"
      :maxlength="maxLength"
      :minLength="minLength"
      :pattern="pattern"
      :max="max"
      :min="min"
      :step="step"
    >
      <slot slot="leading-icon"></slot>
    </md-outlined-text-field>
  </div>
</template>

<style lang="less" scoped></style>
