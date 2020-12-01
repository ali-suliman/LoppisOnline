<template>
  <div class="wrapper">
    <mobile-navbar />
    <Navbar />
    <animated-image />
  </div>
</template>

<script>
import MobileNavbar from "../components/MobileNavbar.vue"
import AnimatedImage from "../components/AnimatedImage.vue"
import Navbar from "../components/Navbar.vue"
export default {
  components: {
    MobileNavbar,
    AnimatedImage,
    Navbar,
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.wrapper {
  width: 100vw;
  @include flex();
}
</style>
