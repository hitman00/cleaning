<template>
  <div
    v-observe-visibility="{
      callback: visibilityChanged,
      throttle: 500,
    }"
  ></div>
</template>

<script>
export default {
  name: 'Visable',
  props: {
    sh: {
      type: Boolean,
      default: false,
    },
  },
  data: () => ({
    show: false,
  }),
  methods: {
    visibilityChanged(isVisible) {
      if (isVisible) {
        this.show = true
      }
    },
  },
}
</script>

<style lang="scss" module></style>
