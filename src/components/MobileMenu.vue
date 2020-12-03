<template>
  <div class="menu">
    <ul>
      <li><a class="exit" @click="exitNav">X</a></li>
      <li><router-link to="/">hem</router-link></li>
      <li><router-link to="/about">om oss</router-link></li>
      <li><router-link to="/contact">kontakta oss</router-link></li>
      <li><router-link to="/download">ladda ner</router-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  methods: {
    exitNav: function() {
      this.$emit("exitNav")
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.menu {
  position: fixed;
  top: 0;
  right: 0;
  width: 100vw;
  height: 100vh;
  background: $main-color;
  z-index: 10;
  @include flex();
  justify-content: flex-start;
  animation: swipeIn 0.8s ease-in forwards;

  ul {
    padding: 3rem 0rem;
    width: 100%;
    list-style: none;
    @include flex();
    align-items: flex-start;

    li {
      width: 100%;
      padding: 0rem 1rem;
      margin: 0.5rem 0rem;
      @include flex();
      justify-content: flex-start;
      align-items: flex-start;

      a {
        width: 100%;
        padding: 1rem 2rem;
        border-radius: 12px;
        color: #eee;
        text-transform: uppercase;
        text-decoration: none;
        font-weight: bold;

        &.router-link-exact-active {
          border: 2px solid #f2f2f2;
        }
      }

      .exit {
        width: initial;
        align-self: flex-end;
      }
    }
  }
}

@keyframes swipeIn {
  0% {
    transform: translateX(1200px);
  }
  100% {
    transform: translateX(0px);
  }
}
</style>
