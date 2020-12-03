<template>
  <div class="login">
    <img class="logo" src="../assets/images/logo.svg" alt="" />
    <form>
      <input type="text" placeholder="Email adress" />
      <input type="text" placeholder="Lösenord" />
      <button>logga in</button>
    </form>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.login {
  @include flex();
  align-items: center;
  justify-content: flex-start;
  width: 100%;
  height: 100vh;
  background: $light-shade;
  padding: 2rem;

  .logo {
    margin: 4rem 0rem;
  }

  form {
    @include flex();
    padding: 3rem 0rem;
    width: 100%;
    margin: 2rem 0rem;
    max-width: 500px;
    width: 100%;
    input {
      @include input-mobile();
    }

    button {
      @include cta-mobile();
      margin: 2rem 0rem;
    }
  }
}

@media screen and (min-width: 1200px) {
  .login {
    form {
      input {
        padding: 1.6rem 2rem;
        font-size: 1rem;
        margin: 0.6rem 0rem;
      }

      button {
        @include cta();
        @include cta-animation();
        margin: 2rem 0rem;
        padding: 1.2rem 2rem;

        &:hover {
          transform: translateY(0.6rem);
          background: #f2f2f2;
        }
      }
    }
  }
}
</style>
