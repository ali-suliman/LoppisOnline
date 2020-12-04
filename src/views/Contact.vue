<template>
  <div class="contact">
    <!-- NAVIGATION  -->

    <mobile-menu v-if="showMenu" @exitNav="closeNav" />
    <navbar />
    <mobile-navbar @menuBtnClicked="showMenuHandler" />

    <!--  -->
    <div class="content">
      <section class="container">
        <h2>kontakta oss.</h2>
        <p>skicka ett medelande till oss och få svar inom 24 timmar</p>

        <div class="contac-info">
          <article class="info">
            <img src="../assets/images/tel.svg" alt="" />
            <p class="title">+46798344511</p>
          </article>
          <article class="info">
            <img src="../assets/images/email.svg" alt="" />
            <p class="title">loppis.online@service.com</p>
          </article>
          <article class="info">
            <img src="../assets/images/gps.svg" alt="" />
            <p class="title">Edeby 4, STÄRNHOV 640 51</p>
          </article>
        </div>
      </section>
      <section class="form-section">
        <contact-form />
      </section>
    </div>

    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue"
import Footer from "../components/Footer.vue"
import MobileNavbar from "../components/MobileNavbar.vue"
import ContactForm from "../components/ContactForm.vue"
import MobileMenu from "../components/MobileMenu.vue"

export default {
  components: {
    Navbar,
    Footer,
    MobileNavbar,
    ContactForm,
    MobileMenu,
  },
  data: () => {
    return {
      showMenu: false,
    }
  },
  methods: {
    showMenuHandler: function() {
      this.showMenu = true
    },
    closeNav: function() {
      console.log("exiting")
      this.showMenu = false
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.contact {
  width: 100%;
  min-height: 100%;
  @include flex();

  .container {
    padding: 6rem 2rem 0rem 2rem;
    width: 100%;
    @include flex();
    align-items: flex-start;

    p {
      color: #666;
      max-width: 30ch;
      margin: 1rem 0rem;
      line-height: 1.5rem;
      font-size: 0.9rem;
    }

    .contac-info {
      width: 100%;
      margin: 2rem 0rem;
      padding: 2rem 0rem;
      @include flex();
      align-items: flex-start;

      .info {
        padding: 0.2rem 1.4rem;
        margin: 0.5rem 0rem;
        border-radius: 10px;
        width: 100%;
        @include flex();
        flex-direction: row;
        justify-content: flex-start;
        border: 2.4px solid $light-shade;

        &:hover {
          background: $light-shade;
        }

        img {
          margin-right: 2rem;
          transform: scale(0.7);
        }

        .title {
          color: #444;
          font-size: 0.8rem;
        }
      }
    }
  }

  .form-section {
    @include flex();
    width: 100%;
    padding: 2rem 1.5rem;
    margin-bottom: 3rem;
  }
}

@media screen and (min-width: 1200px) {
  .contact {
    .container {
      padding: 0rem 6rem 0rem 6rem;
      justify-content: space-between;

      p {
        font-size: 1rem;
      }
      h2 {
        font-size: 1.8rem;
      }
    }
    .content {
      width: 100%;
      @include flex();
      flex-direction: row;

      .contac-info {
        padding: 0rem;
        .info {
          padding: 0.7rem 2rem;
          max-width: 26rem;
          margin: 0.6rem 0rem;

          &:hover {
            transform: translateY(0.4rem);
          }
          .title {
            font-size: 0.9rem;
          }
          img {
            transform: scale(0.9);
          }
        }
      }
    }
  }

  .form-section {
    @include flex();
    max-width: 40vw;
    padding: 2rem 1.5rem;
    margin-bottom: 3rem;
  }
}
</style>
