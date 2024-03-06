<template>
  <div>
    {{ store.count }}-{{ store.doubleCount }}
    <button @click="store.increment()">button</button>
  </div>
</template>

<script setup>
import { useCounterStore } from '@/stores/counter'

const store = useCounterStore()
</script>

<style lang="scss" scoped></style>
