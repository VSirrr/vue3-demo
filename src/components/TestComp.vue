<template>
  <div>
    TestComp
    <slot />
  </div>
</template>

<script>
export default {
  name: 'TestComp',
  // inheritAttrs: false,
  data() {
    return {}
  },
  mounted() {
    console.log(this, 'TestComp')
  },
  created() {
    console.log('created');
  },
  computed: {},
  methods: {}
}
</script>

<style lang="scss" scoped></style>
