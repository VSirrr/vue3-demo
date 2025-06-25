<template>
  <div class="test">
    {{ count }}
    <button @click="increment">button</button>
    <CounterButton />
  </div>
</template>

<script>
import { ref } from 'vue'
import CounterButton from '@/components/CounterButton.vue'
// window.onbeforeunload = function (e) {
//   e.preventDefault()
//   e.returnValue = ''
// }
export default {
  components: {
    CounterButton
  },
  setup() {
    const count = ref(0)

    function increment() {
      count.value++
    }

    return {
      count,
      increment
    }
  },
  beforeRouteLeave(to, from, next) {
    console.log('beforeRouteLeave', to, from)
    next(false)
  }
}
</script>

<style scoped>
.test {
  font-size: 100px;
  color: aqua;
}
</style>
