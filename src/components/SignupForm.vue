<template>
  <div class="form">
    <section class="upper">
      <input type="text" v-model="first" placeholder="Förnamn" />
      <input type="text" v-model="last" placeholder="Efternamn" />
    </section>
    <input type="text" placeholder="Namn" class="name" />
    <input type="email" v-model="email" placeholder="Mailadress" />
    <input type="password" v-model="password" placeholder="Lösenord" />
    <input
      type="password"
      v-model="passwordConfermation"
      placeholder="Bekräfta lösenord"
      @change="passValidation"
    />
    <p class="passErr" v-if="passErr">
      The confermation doesn't match the password given
    </p>
    <button @click="validation">registrera mig</button>
  </div>
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
      //password Error handeling
      passErr: false,
    }
  },
  methods: {
    passValidation: function() {
      if (
        this.password != this.passwordConfermation ||
        this.password === "" ||
        this.passwordConfermation === ""
      ) {
        this.passErr = true
        return false
      } else {
        this.passErr = false
        return true
      }
    },

    validation: function() {
      console.log(this.passValidation())
      if (this.passValidation() === false) {
        alert("please check that all the forms inputs are correct")
      } else {
        this.$router.push("/")
      }
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";

.form {
  margin: 2rem 0rem;
  width: 100%;
  @include flex();
  //background: $light-shade;
  border-radius: 1rem;
  //padding: 1rem;

  .name {
    display: none;
  }

  .upper {
    @include flex();
    flex-direction: row;

    input {
      &:nth-child(1) {
        margin-right: 1rem;

        &:nth-child(2) {
          margin-left: 1rem;
        }
      }
    }
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
  .form {
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
        transform: translateY(0.4rem);
        background: #f2f2f2;
      }
    }
  }
}
</style>
