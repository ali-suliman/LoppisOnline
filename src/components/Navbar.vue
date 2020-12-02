<template>
  <nav>
    <img class="logo" alt="loppisOnline logo" src="../assets/images/logo.svg" />

    <section class="links">
      <router-link to="/">hem</router-link>
      <router-link to="/about">om oss</router-link>
      <router-link to="/contact">kontakta oss</router-link>
      <router-link to="/download">ladda ner</router-link>
    </section>

    <section class="rgstr">
      <button class="signup">skapa konto</button>
      <button>logga in</button>
    </section>
  </nav>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";

nav {
  @include flex();
  flex-direction: row;
  justify-content: flex-start;
  width: 100%;
  padding: 2rem 6rem;

  .links {
    margin: 0rem 3rem;
  }

  a {
    padding: 0.8rem 1rem;
    margin: 0rem 1rem;
    color: #2c3e50;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 0.85rem;
    font-weight: bold;
    font-family: $p-font;

    &.router-link-exact-active {
      color: $main-color;
      border-bottom: 1.9px solid $main-color;
    }

    &:hover {
      color: $main-color;
    }
  }

  .rgstr {
    margin-left: auto;

    button {
      border: none;
      padding: 0.7rem 1.6rem;
      background: none;
      font-weight: bold;
      color: #444;
      font-size: 0.75rem;
      text-transform: uppercase;
      cursor: pointer;
      &:hover {
        color: $main-color;
      }
    }

    .signup {
      margin: 0rem 1rem;
      background: $main-color;
      border-radius: 2rem;
      color: #f2f2f2;
      @include cta-animation();
    }
  }
}

@media screen and (max-width: 1200px) {
  nav {
    display: none;
  }
}
</style>
