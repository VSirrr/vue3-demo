<script setup>
import { ref, watchEffect } from 'vue'
import TestComp from '@/components/TestComp.vue'
import EmitsCopm from '@/components/EmitsCopm.vue'
import PropsComp from '@/components/PropsComp.vue'
import ReactiveComp from '@/components/ReactiveComp.vue'
import CounterButton from '@/components/CounterButton.vue'
import ModelValueComp from '@/components/ModelValueComp.vue'
import ModelValueComp2 from '@/components/ModelValueComp2.vue'
import ImageScale from '@/components/ImageScale.vue'
import ImageScale2 from '@/components/ImageScale2.vue'

const list = ref([1, 2, 3, 5, 4, 9, 7, 8, 0])

function onBtnClick(e) {
  console.log(e)
}

const inputValue = ref('')
const firstName = ref('')
const lastName = ref('')

watchEffect(() => {
  console.log(inputValue.value)
})
</script>

<template>
  <main>
    <!-- <CounterButton />
    <TestComp class="test">test</TestComp>
    <ReactiveComp />
    <PropsComp :list="list" />
    <EmitsCopm @btn-click="onBtnClick" />
    <ModelValueComp v-model.capitalize="inputValue" />
    <div>
      {{ firstName }}-{{ lastName }}
      <br />
      <ModelValueComp2 v-model:first-name="firstName" v-model:last-name="lastName" />
    </div>
    <ImageScale /> -->
    <!-- <ImageScale2 /> -->
  </main>
</template>

<style scoped>
.test {
  color: red;
}
</style>
