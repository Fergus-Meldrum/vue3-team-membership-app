<script setup>
defineProps({
  modelValue: String
})

let emit = defineEmits(['update:modelValue'])
function onTabPress(e) {
  let textarea = e.target

  // get caret position/selection
  let val = textarea.value,
    start = textarea.selectionStart,
    end = textarea.selectionEnd

  // set textarea value to: text before caret + tab + text after caret
  textarea.value = val.substring(0, start) + '\t' + val.substring(end)

  // put caret at right position again
  textarea.selectionStart = textarea.selectionEnd = start + 1
}
</script>

<template>
  <textarea
    v-text="modelValue"
    @keydown.tab.prevent="onTabPress"
    @keyup="emit('update:modelValue', $event.target.value)"
  ></textarea>
</template>

<style scoped></style>
