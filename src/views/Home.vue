<template>
  <div class="home">
    <!-- NAVIGATION  -->

    <mobile-menu v-if="showMenu" @exitNav="closeNav" />
    <navbar />
    <mobile-navbar @menuBtnClicked="showMenuHandler" />

    <!--  -->

    <section class="content">
      <article>
        <blockquote>gör din loppis online</blockquote>
        <p>
          här kan du sälja dina använda saker snabbt och enkelt, genom vår
          digitala tjänst Loppis Online.
        </p>
      </article>

      <animated-image />
      <img src="../assets/images/animation.svg" alt="" />

      <section class="actions">
        <button class="cta animated" @click="toDownload">
          ladda ner appen
        </button>
        <button class="link" @click="toContact">kontakta oss</button>
      </section>
    </section>

    <section class="steps">
      <h3 class="steps-title">Så här använder du LoppisOnline</h3>

      <div class="container">
        <article class="step">
          <img src="../assets/images/list.svg" alt="" />
          <h4>fyll i formularet</h4>
          <p>
            En enkel formular där du beskriver din produkt, lägger till kontakt
            uppgifter och lite annan information.
          </p>
        </article>

        <article class="step">
          <img src="../assets/images/add.svg" alt="" />
          <h4>lägg till produkter</h4>
          <p>
            Fyll på en lista på dem produkterna du vill sälja med bland annat
            bilder och lite info om produkten.
          </p>
        </article>

        <article class="step">
          <img src="../assets/images/wait.svg" alt="" />
          <h4>vänta på köpare</h4>
          <p>
            Vänta på att potentiella köpare ska höra av sig.
          </p>
        </article>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script>
import MobileNavbar from "../components/MobileNavbar.vue"
import Footer from "../components/Footer.vue"
import AnimatedImage from "../components/AnimatedImage.vue"
import Navbar from "../components/Navbar.vue"
import MobileMenu from "../components/MobileMenu.vue"

export default {
  name: "Home",
  components: {
    MobileNavbar,
    Footer,
    AnimatedImage,
    Navbar,
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
    toDownload: function() {
      this.$router.push("/download")
    },
    toContact: function() {
      this.$router.push("/contact")
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";

.home {
  @include flex();
  justify-content: center;

  .content {
    width: 100%;
    text-align: left;
    padding: 1rem 2.6rem;
    @include flex();

    article {
      width: 100%;
      @include flex();
      align-items: center;

      p {
        width: 36ch;
        color: #666;
        font-size: 0.9rem;
        text-align: center;

        &::first-letter {
          text-transform: uppercase;
        }
      }

      blockquote {
        color: #222;
        font-size: bold;
        font-family: $title-font;
        font-size: 1.2rem;
        font-weight: bold;
        text-transform: uppercase;
        margin: 2rem 0rem 1rem 0rem;
      }
    }

    img {
      align-self: center;
      margin: -2rem 0rem;
      transform: scale(0.6);
    }

    .actions {
      width: 100%;
      @include flex();

      button {
        @include cta-mobile();
      }

      .link {
        background: none;
        color: $main-color;
      }
    }
  }

  .steps {
    clip-path: polygon(0 4%, 100% 0%, 100% 100%, 0% 100%);
    width: 100vw;
    min-height: 100vh;
    @include flex();
    background: $light-shade;
    margin-top: 1rem;
    padding: 8rem 2rem;

    .steps-title {
      text-align: center;
      max-width: 20ch;
      line-height: 1.9rem;
      margin: 4rem 0rem;
    }

    .container {
      text-align: center;
      @include flex();
      .step {
        @include flex();
        width: 70%;
        margin: 3rem 0rem;

        img {
          margin: 2rem 1rem;
          transform: scale(0.8);
        }

        h4 {
          text-transform: uppercase;
        }

        p {
          text-align: center;
          margin: 1rem;
          color: #666;
          max-width: 18rem;
        }
      }
    }
  }
}

@media screen and (min-width: 760px) {
  .home {
    .content {
      article {
        margin: 2.5rem 0rem;
        p,
        blockquote {
          align-self: center;
        }
      }
      .actions {
        button {
          width: 60%;
        }
      }
    }
    .steps {
      .steps-title {
        align-self: center;
        width: initial;
        line-height: 1.9rem;
        margin: 4rem 0rem;
      }
    }
  }
}

// ========= DISKTOP VIEW ========= //

@media screen and (min-width: 1200px) {
  .home {
    .content {
      padding: 3rem 6rem;
      display: grid;
      grid-template-rows: repeat(5, 8rem);
      grid-template-columns: repeat(5, 1fr);
      grid-template-areas:
        "header header header  . ."
        "header header header  . ."
        "header header header  img img"
        "act act act  img img"
        ". . . .  .";

      article {
        display: block;
        grid-area: header;
        blockquote {
          font-size: 3rem;
          margin: 3rem 0rem 0rem 0rem;
        }

        p {
          font-size: 1.1rem;
          width: 50ch;
          margin: 1rem 0rem 2rem 0rem;
          line-height: 2.1rem;
          text-align: left;
        }
      }

      img {
        display: none;
      }

      .actions {
        grid-area: act;
        flex-direction: row;
        justify-content: flex-start;
        margin-bottom: 2rem;

        button {
          width: initial;
          @include cta();
          &:hover {
            transform: translateY(0.3rem);
          }
        }

        .animated {
          @include cta-animation();
        }
      }
    }

    .steps {
      clip-path: polygon(0 9%, 100% 0, 100% 100%, 0% 100%);
      padding: 10rem 6rem;
      margin-top: -2.5rem;

      .steps-title {
        font-size: 1.6rem;
        margin: 5rem 0rem;
        max-width: 40rem;
      }

      .container {
        flex-direction: row;
        padding: 0rem 2rem;
        .step {
          padding: 4rem;
          border-radius: 10px;
          @include stepAnim();

          p {
            color: #888;
          }

          &:hover > p {
            color: #222;
          }

          img {
            margin: 5rem 0rem;
            transform: scale(1);
          }

          h4 {
            font-size: 1.1rem;
            margin: 1rem 0rem;
          }
        }
      }
    }
  }
}
</style>
