<script setup>
const props = defineProps({
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
  value: String,
  error: Boolean,
  errorText: String,
  label: String,
  prefixText: String,
  suffixText: String,
  hasLeadingIcon: Boolean,
  hasTrailingIcon: Boolean,
  supportingText: String,
  textDirection: String,
  rows: Number,
  cols: Number,
  inputMode: String,
  max: String,
  maxLength: Number,
  min: String,
  minLength: Number,
  pattern: String,
  readOnly: Boolean,
  multiple: Boolean,
  step: String,
  type: String,
  autocomplete: String
})
</script>

<template>
  <div class="default"></div>
</template>

<style lang="less" scoped></style>
