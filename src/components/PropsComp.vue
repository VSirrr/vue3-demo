<template>
  <div>
    <ul>
      <li v-for="i in list" :key="i">{{ i }}</li>
    </ul>
    <button @click="onClick">button</button>
  </div>
</template>

<script setup>
const porps = defineProps({
  list: {
    type: Array,
    default: () => []
  }
})

/* 
  更改对象/数组类型的 props
  
  当对象或数组作为 props 被传入时，虽然子组件无法更改 props 绑定，但仍然可以更改对象或数组内部的值。这是因为 JavaScript 的对象和数组是按引用传递，而对 Vue 来说，禁止这样的改动，虽然可能生效，但有很大的性能损耗，比较得不偿失。

  这种更改的主要缺陷是它允许了子组件以某种不明显的方式影响父组件的状态，可能会使数据流在将来变得更难以理解。在最佳实践中，你应该尽可能避免这样的更改，除非父子组件在设计上本来就需要紧密耦合。在大多数场景下，子组件应该抛出一个事件来通知父组件做出改变。 
*/
function onClick() {
  // eslint-disable-next-line vue/no-mutating-props
  porps.list.sort((a, b) => a - b)
}
</script>

<style lang="scss" scoped></style>
