<template>
  <div class="contact">
    <Navbar />
    <section class="contact">
      <h2>kontakta oss</h2>
      <p>skicka ett medelande till oss och få svar inom<b>24 timmar</b></p>

      <div class="contac-infot">
        <article class="info">
          <img src="../assets/images/tel.svg" alt="" />
          <p class="title">tel</p>
          <p>+46798344511</p>
        </article>
        <article class="info">
          <img src="../assets/images/email.svg" alt="" />
          <p class="title">email</p>
          <p>loppis.online@service.com</p>
        </article>
        <article class="info">
          <img src="../assets/images/gps.svg" alt="" />
          <p class="title">adress</p>
          <p>Edeby 4, STÄRNHOV 640 51</p>
        </article>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue"
import Footer from "../components/Footer.vue"
export default {
  components: {
    Navbar,
    Footer,
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
.contact {
  width: 100%;
  min-height: 100%;
}
</style>
