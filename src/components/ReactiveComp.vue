<template>
  <div>
    {{ state.count.value }}
    <button @click="state.count.value++">button</button>
  </div>
</template>

<script setup>
import { reactive, /* shallowReactive */ onBeforeMount, onBeforeUpdate, watchEffect } from 'vue'
const state = reactive({
  count: {
    value: 0
  }
})

onBeforeMount(() => {
  console.log('onBeforeMount')
})

onBeforeUpdate(() => {
  console.log('onBeforeUpdate')
})

watchEffect(() => {
  console.log(state.count.value)
})
</script>

<style lang="scss" scoped></style>
