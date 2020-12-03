<template>
  <div class="about">
    <!-- NAVIGATION  -->

    <mobile-menu v-if="showMenu" @exitNav="closeNav" />
    <navbar />
    <mobile-navbar @menuBtnClicked="showMenuHandler" />

    <!--  -->

    <section class="txt">
      <h3><span class="capital">loppis online</span></h3>
      <p>
        Är en ny startad företag som hjälper folk att utföra sin loppismarknad
        digitalt för att sälja sina gammla eller användade saker snabbt och
        enkelt.
      </p>
      <p>
        På grund av Corona krisen just nu är det svårt att ha personlig kontakt
        med folk, därför kom vi på idén att göra loppismarnaden till en online
        tjänst istället, för att hjälpa folk att tjäna extra pengar.
      </p>
    </section>
    <section class="txt colored-bg">
      <h3>varför startade vi <span class="capital">loppis online</span>?</h3>
      <p>
        Vi startade Loppis Online eftersom under Corona krisen så minskade
        besöken på Loppis affärer.
      </p>
      <p>
        Vi såg att det fanns en möjlighet för Loppisar runt om i Sverige, för
        att de saknade en Webshop och E-handel sida.
      </p>
      <p>
        Loppisarna och Secondhand affärer saknade en gemensam plattform där dem
        kunde sälja sina produkter online. Vi ville underlätta och skapa
        möjlighet för köpare och säljare att mötas online och genomföra en säker
        digital handel och trygg affär.
      </p>
    </section>
    <section class="txt">
      <h3>hur gör vi för att sälja dina produkter online?</h3>
      <p>
        Att sälja produkter online har aldrig varit lättare än idag. Det räcker
        med att du har tillgång till en mobilkamera som du tar bild på dina
        produkter som du vill sälja online. Du fyller i en annons formulär samt
        lägger till bilder på produkter som du vill sälja online.
      </p>
      <p>
        Våran sida Loppis Online är en annons plattform där du kan som Loppis
        ägare lägga upp dina produkter som du vill sälja online.
      </p>
    </section>
    <Footer />
  </div>
</template>

<script>
import MobileNavbar from "../components/MobileNavbar.vue"
import Navbar from "../components/Navbar.vue"
import Footer from "../components/Footer.vue"
import MobileMenu from "../components/MobileMenu.vue"

export default {
  components: {
    MobileNavbar,
    Navbar,
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
.about {
  width: 100vw;
  @include flex();

  .txt {
    width: 100%;
    padding: 10rem 2.5rem;

    h3 {
      margin: 1.4rem 0rem;
      line-height: 1.9rem;
      &::first-letter {
        text-transform: uppercase;
      }

      .capital {
        text-transform: capitalize;
      }
    }

    p {
      color: #888;
      max-width: 80ch;
    }
  }

  .colored-bg {
    clip-path: polygon(0 7%, 100% 0%, 100% 93%, 0% 100%);
    background: $light-shade;
  }
}

@media screen and (min-width: 700px) {
  .about {
    .txt {
      @include flex();
      text-align: left;
      h3 {
        font-size: 1.6rem;
        margin: 2rem 0rem;
      }
      p {
        margin: 0.8rem 0rem;
        max-width: 60ch;
        line-height: 2.4rem;
        font-size: 1.15rem;
      }
    }
  }
}
</style>
