<template>
  <div>
    <footer ref="myfootercontainer" class="footer">
      <div class="footer-container">
        <b-container>
          <b-row>
            <b-col><h2 class="h_impressum">
              <a class="impressumheader" @click="showImpressumHandler">
              Impressum</a></h2></b-col>
          </b-row>
          <b-row>
            <b-col>
              <Impressum v-if="showImpressum" />
          </b-col>
          </b-row>
          <b-row class="flags-row">
            <b-col class="justify-content-center">
              <img class="nonbinary-logo"
              src="../../public/static/Nonbinary_Gender_Symbol.svg"
              title="Nonbinary Gender Symbol"
              alt="Nonbinary Gender Symbol">
            </b-col>
          </b-row>
        </b-container>
        <div class="nonbinary-banner"></div>
      </div>
    </footer>
  </div>
</template>

<script>
import Impressum from './MyContent/Impressum.vue';

export default {
  name: 'MyFooter',
  components: {
    Impressum,
  },
  data() {
    return {
      showImpressum: false,
    };
  },
  methods: {
    showImpressumHandler() {
      this.showImpressum = !this.showImpressum;
      if (this.showImpressum) {
        this.$nextTick(() => {
          this.$refs.myfootercontainer.scrollIntoView({ block: 'start', behavior: 'smooth' });
          window.addEventListener('scroll', this.handleScroll);
        });

        this.$matomo.trackEvent('click', 'Impressum');
      }
    },
    handleScroll() {
      window.removeEventListener('scroll', this.handleScroll);
    },
  },
};
</script>

<style scoped>

.h_impressum {
  font-size: 1rem;
  margin-top: 1rem;
  margin-bottom: 1rem;
  line-height: 28px;
}

.h_impressum a {
  color: #adb5bd;
}

.footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 160px; /*Set the fixed height of the footer here */
  line-height: 60px; /* Vertically center the text there */
}

.footer-container {
  background-color: #181818;
}

.nonbinary-logo {
  height: 50px;
  filter: invert(100%) sepia(0%);
  font-size: 3em;
}

.nonbinary-banner {
  margin-top: 10px;
  min-height: 30px;
  background-image: linear-gradient(180deg, #FFF430 25%,
    #FFFFFF 25%, 50%, #9C59D1 50%, 75%, #181818 75%);
}

.impressum {
  color:#FFFFFF;
  line-height: 1.5;
  margin-top: 2em;
  margin-bottom: 6em;
}

.impressumheader {
  cursor: pointer;
  text-decoration: underline;
}
</style>
