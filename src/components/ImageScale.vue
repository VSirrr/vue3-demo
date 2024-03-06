<template>
  <div class="root" :ref="setRef">
    <div class="point">
      <div class="canvas">
        <!-- your content here -->
        <img
          src="https://img5.bitautoimg.com/usercenter/cargroup/car/20240110/567/w592_yichecar_202401104709488081556790704.jpg.webp"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { create } from 'pinch-zoom-pan'
import { ref, onMounted, onUnmounted } from 'vue'

const wrap = ref(null)
const canvas = ref(null)

function setRef(ref) {
  wrap.value = ref
}

onMounted(() => {
  // Run module on mount
  console.log(wrap.value, 'wrap.value')
  canvas.value = create({
    element: wrap.value,
    // optional settings:
    minZoom: 0.5,
    maxZoom: 2,
    captureWheel: true
  })
})

onUnmounted(() => {
  canvas.value.destroy() // Should be called on unmount

  // Reset position and zoom to default values
  canvas.value.reset()
})
</script>

<style scoped>
.root {
  position: relative;
  transform: translateZ(0);
  /* overflow: hidden; */
}

.point {
  position: absolute;
  width: 0;
  height: 0;
  transform: translate(0, 0) scale(1);
  transform-origin: center;
  will-change: transform;
}

.canvas {
  position: absolute;
  transform: translate(-50%, -50%);
}
</style>
