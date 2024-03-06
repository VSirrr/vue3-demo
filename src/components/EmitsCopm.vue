<template>
  <div>
    <button @click="onClick">button</button>
  </div>
</template>

<script setup>
const emit = defineEmits(['btnClick'])

function onClick(e) {
  emit('btnClick', e)
}
</script>

<style lang="scss" scoped></style>
