<template>
  <nav>
    <img src="../assets/images/logo.svg" alt="" class="logo" />
    <div class="menu" @click="menuBtnHandler">
      <div class="menuBars"></div>
      <div class="menuBars lower"></div>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    menuBtnHandler: function() {
      this.$emit("menuBtnClicked")
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";

nav {
  width: 100%;
  min-height: 4rem;
  @include flex();
  flex-direction: row;
  justify-content: space-between;
  padding: 1.5rem 0rem 1.5rem 2rem;

  .logo {
    transform: scale(0.8);
  }

  .menu {
    width: 5rem;
    height: 3rem;
    background: $main-color;
    @include flex();
    flex-direction: column;
    justify-content: center;
    border-top-left-radius: 2rem;
    border-bottom-left-radius: 2rem;
    transform: translateX(1rem);
    transition: all 0.4s ease;
    box-shadow: 0px 0px 6px $main-color;

    .menuBars {
      background: #f2f2f2;
      width: 1rem;
      height: 0.2rem;
      border-radius: 2rem;
      margin: 0.15rem 0rem;
    }

    .lower {
      transform: translateX(-0.5rem);
      transition: all 0.4s ease;
    }

    &:hover {
      transform: translateX(0rem);
    }

    &:hover > .lower {
      transform: translateX(0rem);
    }
  }
}
@media screen and (min-width: 1200px) {
  nav {
    display: none;
  }
}
</style>
