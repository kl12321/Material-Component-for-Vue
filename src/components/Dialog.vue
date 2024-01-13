<script setup>
import '@material/web/dialog/dialog.js'
import { ref } from 'vue'

import '@material/web/button/filled-button.js'
import '@material/web/button/filled-tonal-button.js'
import '@material/web/button/text-button.js'
import '@material/web/dialog/dialog.js'
import '@material/web/icon/icon.js'
import '@material/web/iconbutton/icon-button.js'
import '@material/web/radio/radio.js'
import '@material/web/textfield/filled-text-field.js'

//定义属性
const props = defineProps({
  open: Boolean,
  title: String,
  content: String,
  actions: Array,
  onClose: Function
})
const dialog = ref(null)
const handleClose = (e) => {
  console.log(dialog.value.returnValue)
}
</script>

<template>
  <div class="default">
    <md-dialog :open="open" type="alert" ref="dialog" @closed="handleClose">
      <div slot="headline">{{ title }}</div>
      <form slot="content" id="form-id" method="dialog">
        {{ content }}
      </form>
      <div slot="actions">
        <template v-if="actions && actions.length">
          <md-text-button
            v-for="(action, index) in actions"
            :key="index"
            value="cancel"
            form="form-id"
          >
            {{ action }}
          </md-text-button>
        </template>
      </div>
    </md-dialog>
  </div>

</template>

<style lang="less" scoped></style>
