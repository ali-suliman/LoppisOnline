<template>
  <nav id="nav">
    <img alt="Vue logo" src="../assets/images/logo.svg" />

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
#nav {
  padding: 30px;

  a {
    padding: 1rem;
    margin: 0rem 1rem;
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
