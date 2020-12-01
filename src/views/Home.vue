<template>
  <div class="wrapper">
    <mobile-navbar />
    <section class="text-content">
      <blockquote>gör din loppis online</blockquote>
      <p>
        här kan du sälja dina användade saker snabbt och änkelt, genom vår
        digitala loppismarknad servise.
      </p>
    </section>

    <img src="../assets/images/animation.svg" alt="" />

    <section class="actions">
      <button class="cta">ladda ner</button>
      <button class="link">kontakta oss</button>
    </section>

    <section class="steps">
      <h3 class="steps-title">Så här använder du LoppisOnline</h3>

      <article class="step">
        <img src="../assets/images/list.svg" alt="" />
        <h4>fyll i formularet</h4>
        <p>
          En enkel formular där du beskriver din produkt, lägger till kontakt
          uppgifter och lite annat
        </p>
      </article>

      <article class="step">
        <img src="../assets/images/add.svg" alt="" />
        <h4>lägg till produkter</h4>
        <p>
          En enkel formular där du beskriver din produkt, lägger till kontakt
          uppgifter och lite annat
        </p>
      </article>

      <article class="step">
        <img src="../assets/images/wait.svg" alt="" />
        <h4>vänta på köpare</h4>
        <p>
          En enkel formular där du beskriver din produkt, lägger till kontakt
          uppgifter och lite annat
        </p>
      </article>
    </section>
    <Footer />
  </div>
</template>

<script>
import MobileNavbar from "../components/MobileNavbar.vue"
import Footer from "../components/Footer.vue"
export default {
  name: "Home",
  components: {
    MobileNavbar,
    Footer,
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";

.wrapper {
}
@media screen and (max-width: 1024px) {
  .wrapper {
    @include flex();
    justify-content: center;

    .text-content {
      text-align: left;
      padding: 1rem 2.6rem;
      @include flex();
      align-items: flex-start;

      p {
        color: #666;
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
      transform: scale(0.6);
      margin: -2rem 0rem;
    }

    .actions {
      width: 100%;
      @include flex();

      button {
        @include cta();
      }

      .link {
        background: none;
        color: $main-color;
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
        align-self: flex-start;
        width: 20ch;
        line-height: 1.9rem;
        margin: 4rem 0rem;
      }

      .step {
        @include flex();
        width: 70%;
        margin: 1rem 0rem;

        img {
          margin: 1rem;
        }

        h4 {
          text-transform: uppercase;
        }

        p {
          text-align: center;
          margin: 1rem;
        }
      }
    }
  }
}
</style>
