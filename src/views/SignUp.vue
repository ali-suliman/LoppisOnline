<template>
  <div class="signup">
    <section class="txt-section">
      <h2>loppisonline.se</h2>
      <p>
        Fyll i formuläret och börja köpa och sälja direkt!
      </p>
    </section>
    <section class="form-section">
      <signup-form />
      <section class="links">
        <p>har du redan ett konto? <span @click="login">logga in</span></p>
      </section>
    </section>
  </div>
</template>

<script>
import SignupForm from "../components/SignupForm.vue"
export default {
  components: {
    SignupForm,
  },
  methods: {
    login: function() {
      this.$router.push("/login")
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.signup {
  width: 100%;
  height: 100vh;
  padding: 1rem 2.4rem;
  @include flex();
  justify-content: flex-start;
  background: $light-shade;

  section {
    width: 100%;
    @include flex();
    align-items: center;
    text-align: center;
  }

  .txt-section {
    margin: 2rem 0rem 1rem 0rem;
    h2 {
      margin: 2rem 0rem 1rem 0rem;
    }

    p {
      color: #444;
      padding: 0rem 2.6rem;
    }
  }

  .form-section {
    margin: 2rem 0rem 0rem 0rem;
    @include flex();
    height: 100%;
    max-width: 500px;

    .links {
      padding: 2rem 0rem;
      margin-top: auto;
      p {
        font-size: 0.8rem;
        font-weight: bold;
        color: #555;

        span {
          color: $links-color;
          border-bottom: 1.5px solid $links-color;
          cursor: pointer;
        }
      }
    }
  }
}

@media screen and (min-width: 1200px) {
  .signup {
    .form-section {
      .links {
        p {
          font-size: 1rem;
        }
      }
    }
  }
}
</style>
