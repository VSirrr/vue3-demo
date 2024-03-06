<template>
  <input type="text" :value="modelValue" @input="onInput" />
</template>

<script setup>
const props = defineProps({
  modelValue: String,
  modelModifiers: { default: () => ({}) }
})

const emit = defineEmits(['update:modelValue'])

function onInput(e) {
  let value = e.target.value
  if (props.modelModifiers.capitalize) {
    value = value.toUpperCase()
  }
  emit('update:modelValue', value)
}
</script>

<style lang="scss" scoped></style>
