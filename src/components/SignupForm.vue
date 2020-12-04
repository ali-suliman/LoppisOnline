<template>
  <form>
    <section class="upper">
      <input type="text" v-model="first" placeholder="Förnamn" />
      <input type="text" v-model="last" placeholder="Efternamn" />
    </section>
    <input type="text" placeholder="Namn" />
    <input type="email" v-model="email" placeholder="Mailadress" />
    <input type="password" v-model="password" placeholder="Lösenord" />
    <input
      type="password"
      v-model="passwordConfermation"
      placeholder="Bekräfta lösenord"
    />
    <button @click="enterSite">registrera mig</button>
  </form>
</template>

<script>
export default {
  data: () => {
    return {
      first: "",
      last: "",
      number: "",
      email: "",
      password: "",
      passwordConfermation: "",
    }
  },
  methods: {
    enterSite: function() {
      this.$router.push("/")
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";

form {
  margin: 2rem 0rem;
  width: 100%;
  @include flex();
  //background: $light-shade;
  border-radius: 1rem;
  //padding: 1rem;

  .upper {
    display: none;
  }

  input {
    @include input-mobile();
  }

  button {
    @include cta-mobile();
    padding: 0.9rem 2rem;
    margin: 1.8rem 0rem;
    width: 80%;
  }
}

@media screen and (min-width: 1200px) {
  form {
    input {
      margin: 0.5rem 0rem;
      padding: 1.4rem 2rem;
      font-size: 1rem;
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
</style>
