<template>
  <div :class="$style.star_main">
    <div v-for="id in full" :key="'full' + id" :class="$style.fix">
      <img src="@/assets/imgs/star.png" />
    </div>
    <div v-for="id in empty" :key="'empty' + id" :class="$style.fix">
      <img src="@/assets/imgs/star2.png" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Stars',
  props: {
    full: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    empty() {
      return 5 - this.full
    },
  },
}
</script>

<style lang="scss" module>
.star_main {
  display: flex;
}

.fix {
  margin-right: 4%;
}
</style>
