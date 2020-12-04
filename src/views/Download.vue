<template>
  <div class="download">
    <!-- NAVIGATION  -->

    <mobile-menu v-if="showMenu" @exitNav="closeNav" />
    <navbar />
    <mobile-navbar @menuBtnClicked="showMenuHandler" />

    <!--  -->

    <div class="container">
      <section class="content">
        <blockquote>ladd ner <span>loppis online</span>.</blockquote>
        <p class="txt">
          Här kan du lätt och änkelt sälja dina gamla saker genom att skapa din
          egen loppismarknad online.
        </p>
        <section class="actions">
          <a class="btn">
            <img src="../assets/images/appstore.svg" alt="" />
            <p>app store</p>
          </a>
          <a class="btn">
            <img src="../assets/images/googleplay.svg" alt="" />
            <p>google play</p>
          </a>
        </section>
      </section>

      <section class="animation">
        <img src="../assets/images/download.svg" alt="" />
      </section>

      <section class="actions-mobile">
        <a class="btn">
          <img src="../assets/images/appstore.svg" alt="" />
          <p>app store</p>
        </a>
        <a class="btn">
          <img src="../assets/images/googleplay.svg" alt="" />
          <p>google play</p>
        </a>
      </section>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue"
import MobileNavbar from "../components/MobileNavbar.vue"
import Footer from "../components/Footer.vue"
import MobileMenu from "../components/MobileMenu.vue"

export default {
  components: {
    Navbar,
    MobileNavbar,
    Footer,
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
.download {
  width: 100%;
  @include flex();
  justify-content: space-between;
  .container {
    width: 100%;
    @include flex();
    justify-content: flex-start;
    padding: 1rem 2rem;

    .content {
      padding: 2rem 1rem;

      .actions {
        display: none;
      }

      blockquote {
        font-size: 1.3rem;
        font-weight: bold;
        font-family: $title-font;
        margin: 1rem 0rem;

        &:first-letter {
          text-transform: uppercase;
        }

        span {
          text-transform: capitalize;
        }
      }
      p {
        color: #666;
        max-width: 50ch;
      }
    }

    .animation {
      margin: 2rem 0rem;
      img {
        width: 280px;
      }
    }

    .actions-mobile,
    .actions {
      padding: 1rem;
      margin: 1rem 0rem 3rem 0rem;
      @include flex();
      width: 100%;

      .btn {
        display: flex;
        justify-content: center;
        border-radius: 10px;
        margin: 1rem 0rem;
        padding: 1.2rem;
        background: #222;
        border: none;
        width: 86%;
        color: #fefefe;
        text-transform: capitalize;

        p {
          margin: 0rem 1rem;
        }
      }
    }
  }
}

@media screen and (min-width: 760px) {
  .download {
    .container {
      padding: 4rem 22%;

      .animation {
        margin: 4rem 0rem;
        img {
          width: 400px;
        }
      }
    }
  }
}

@media screen and (min-width: 1380px) {
  .download {
    .container {
      flex-direction: row;
      justify-content: space-between;
      align-items: flex-start;
      padding: 4rem 6rem 6rem 6rem;

      .content {
        padding: 6rem 2rem;
        margin-top: 3rem;

        blockquote {
          font-size: 3rem;
        }

        .txt {
          font-size: 1.1rem;
        }

        .actions {
          display: flex;
          margin: 6rem 0rem 0rem 0rem;
          padding: 1rem 0rem;
          flex-direction: row;
          justify-content: space-between;
          max-width: 36rem;

          a {
            width: initial;
            padding: 1rem 4rem;
            cursor: pointer;

            &:hover {
              background: #f2f2f2;
              transform: translateY(0.5rem);
            }

            &:hover > p {
              color: #222;
            }
            p {
              color: #f2f2f2;
              font-weight: bold;
            }
          }
        }
      }

      .animation {
        margin: 1rem 0rem 4rem 0rem;
        padding: 0rem 6rem 0rem 0rem;
        img {
          width: 480px;
        }
      }

      .actions-mobile {
        display: none;
      }
    }
  }
}
</style>
