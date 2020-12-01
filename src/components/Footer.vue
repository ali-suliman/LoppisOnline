<template>
  <footer>
    <section class="kontakt">
      <h3>har du några frågor?</h3>
      <p>tveka inte att <a href="#">kontakta oss</a></p>
    </section>
    <section class="links">
      <article>
        <p class="list-title">länkar</p>
        <ul>
          <li><a href="#">huvudsidan</a></li>
          <li><a>om oss</a></li>
          <li><a href="#">kontakta oss</a></li>
          <li><a href="#">ladda ner</a></li>
        </ul>
      </article>
      <article>
        <p class="list-title">annat</p>
        <ul>
          <li><a href="#">privacy policy</a></li>
          <li><a href="#">terms of use</a></li>
        </ul>
      </article>
    </section>
    <section class="social-media">
      <p class="loppis">loppisonline.se</p>
      <article class="socials">
        <img src="../assets/images/instagram.svg" alt="" />
        <img src="../assets/images/facebook.svg" alt="" />
        <img src="../assets/images/twitter.svg" alt="" />
      </article>
    </section>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
footer {
  background: #222;
  width: 100%;
  padding: 2rem 0rem;
  @include flex();

  section {
    width: 100%;
    @include flex();
    color: #fefefe;
    margin-top: 2rem;
    padding: 1rem 2rem;

    a {
      color: #999;
      text-decoration: none;
      text-transform: uppercase;
      font-size: 0.7rem;
    }
  }

  .kontakt {
    align-items: flex-start;

    h3 {
      &::first-letter {
        text-transform: uppercase;
      }
    }
    p {
      margin: 0.2rem 0rem;
      color: #e2e2e2;
      font-size: 0.8rem;
      &::first-letter {
        text-transform: uppercase;
      }
    }
    a {
      text-decoration: underline;
      text-transform: none;
      font-weight: bold;
      padding: 0rem 0.2rem;
    }
  }

  .links {
    @include flex();
    flex-direction: row;
    align-items: flex-start;
    justify-content: flex-start;

    article {
      margin-right: 3rem;

      .list-title {
        &::first-letter {
          text-transform: uppercase;
        }
        font-weight: bold;
        font-size: 0.8rem;
        margin: 1rem 0rem;
        border-bottom: #444 solid 2px;
        padding: 0.6rem 0rem;
      }

      ul {
        list-style: none;

        li {
          margin: 0.4rem 0rem;
        }
      }
    }
  }

  .social-media {
    width: 100%;
    margin: 2rem 0rem;
    @include flex();
    flex-direction: row;
    justify-content: space-between;

    .loppis {
      font-size: 0.7rem;
      font-weight: bold;
      font-family: $title-font;
    }

    .socials {
      img {
        transform: scale(0.9);
        padding: 0rem 0.8rem;
      }
    }
  }
}
</style>
