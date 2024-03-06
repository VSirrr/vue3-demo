<template>
  <div class="root" :ref="setRef">
    <img
      src="https://img5.bitautoimg.com/usercenter/cargroup/car/20240110/567/w592_yichecar_202401104709488081556790704.jpg.webp"
    />
  </div>
</template>

<script setup>
import PinchZoom from 'pinch-zoom-js'
import { ref, onMounted, onUnmounted } from 'vue'
// console.log(PinchZoom, 'PinchZoom')

const wrap = ref(null)
const canvas = ref(null)

function setRef(ref) {
  wrap.value = ref
}

onMounted(() => {
  // Run module on mount
  new PinchZoom(wrap.value, {
    minZoom: 1,
    useMouseWheel: true
  })
})

onUnmounted(() => {})
</script>

<style scoped>
.root {
  position: relative;
  transform: translateZ(0);
  height: 500px;
}
</style>
