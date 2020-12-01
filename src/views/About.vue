<template>
  <div class="wrapper">
    <mobile-navbar />
  </div>
</template>

<script>
import MobileNavbar from "../components/MobileNavbar.vue"
export default {
  components: {
    MobileNavbar,
  },
}
</script>

<style lang="scss" scoped>
.wrapper {
  width: 100vw;
}
</style>
