<template>
  <article class="socials">
    <img src="../assets/images/instagram.svg" alt="" />
    <img src="../assets/images/facebook.svg" alt="" />
    <img src="../assets/images/twitter.svg" alt="" />
  </article>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.socials {
  img {
    transform: scale(0.9);
    padding: 0rem 0.8rem;
    cursor: pointer;
  }
}

@media screen and (min-width: 1200px) {
  .socials {
    img {
      transform: scale(1.4);
      margin: 0rem 1rem;

      &:hover {
        transform: scale(1.6);
      }
    }
  }
}
</style>
