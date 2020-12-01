<template>
  <div class="image-wrapper">
    <img src="../assets/images/animation-row.svg" alt="" />
    <img class="dollar la" src="../assets/images/dollar.svg" alt="" />
    <img class="dollar md" src="../assets/images/dollar.svg" alt="" />
    <img class="dollar sm" src="../assets/images/dollar.svg" alt="" />
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.image-wrapper {
  position: relative;
  width: 30vw;
  @include flex();
  grid-area: img;
  justify-self: flex-end;
  margin: 1rem 2rem 8rem 0rem;
}

img {
  max-width: 120%;
  transform: scale(1.05);
}

.dollar {
  animation: 0.8s dollarAnimation infinite ease-in-out alternate;
  position: absolute;
}

.la {
  right: 4%;
  top: 36%;
}

.md {
  left: 8%;
  bottom: 32%;
  max-width: 1.85rem;
  animation: 0.8s dollarAnimationRE infinite ease-in-out alternate;
}

.sm {
  top: 2%;
  right: 32%;
  width: 1.5rem;
  animation-duration: 0.65s;
}

@keyframes dollarAnimation {
  0% {
    transform: rotate(20deg);
  }

  100% {
    transform: rotate(-20deg);
  }
}

@keyframes dollarAnimationRE {
  0% {
    transform: rotate(-20deg);
  }

  100% {
    transform: rotate(20deg);
  }
}

@media screen and (max-width: 1200px) {
  .image-wrapper {
    display: none;
  }
}
</style>
