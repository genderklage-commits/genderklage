<template>
  <div>
    <h2 id="Supporter"
    data-track-content data-content-name="Content" data-content-piece="Supporter">
      Unterstützer*innen</h2>
    <p>Vielen Dank für die Unterstützung aus der Community &amp; alle die sich hinter das
      Projekt und das Anliegen stellen! Die Logos sind verlinkt,
      Organisationen sind in zufälliger Reihenfolge
      aufgelistet (<a href="#"
      style="cursor: pointer;" @click="shuffle">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-shuffle" viewBox="0 0 16 16">
        <path fill-rule="evenodd" d="M0 3.5A.5.5 0 0 1 .5 3H1c2.202 0 3.827 1.24 4.874
        2.418.49.552.865 1.102 1.126 1.532.26-.43.636-.98 1.126-1.532C9.173 4.24 10.798
        3 13 3v1c-1.798 0-3.173 1.01-4.126 2.082A9.624 9.624 0 0 0 7.556 8a9.624 9.624
        0 0 0 1.317 1.918C9.828 10.99 11.204 12 13 12v1c-2.202 0-3.827-1.24-4.874-2.418A10.595
        10.595 0 0 1 7 9.05c-.26.43-.636.98-1.126 1.532C4.827 11.76 3.202 13 1 13H.5a.5.5
        0 0 1 0-1H1c1.798 0 3.173-1.01 4.126-2.082A9.624 9.624 0 0 0 6.444 8a9.624 9.624 0
        0 0-1.317-1.918C4.172 5.01 2.796 4 1 4H.5a.5.5 0 0 1-.5-.5z"/>
        <path d="M13 5.466V1.534a.25.25 0 0 1 .41-.192l2.36 1.966c.12.1.12.284 0
        .384l-2.36 1.966a.25.25 0 0 1-.41-.192zm0 9v-3.932a.25.25 0 0 1 .41-.192l2.36
        1.966c.12.1.12.284 0 .384l-2.36 1.966a.25.25 0 0 1-.41-.192z"/>
      </svg>
      shuffle</a>):</p>

    <div class="supporter container">
      <FlipCards ref="supporter" :items='supporters' />
    </div>

    <div class="partners container">
      <h3>Kooperationsparnter*innen</h3>
      <FlipCards ref="partner" :items='partners' />
    </div>

  </div>
</template>

<script>
import FlipCards from './FlipCards.vue';

export default {
  name: 'Supporters',
  components: {
    FlipCards,
  },
  data() {
    return {
      publicPath: process.env.BASE_URL,
      supporters: [
        {
          img: 'static/logos/rkl.png',
          name: 'Rechtskomitee Lambda',
          type: 'rkl',
          url: 'https://www.rklambda.at/',
          statement: 'Die Freiheit, die eigene Geschlechts&shy;identität zu bestimmen, gehört zu den grundlegendsten Wesens&shy;bereichen der Selbst&shy;bestimmung',
        },
        {
          img: 'static/logos/vimoe.png',
          name: 'VIMÖ - Verein Intergeschlechtlicher Menschen Österreich',
          type: 'vimoe',
          url: 'https://vimoe.at/',
        },
        {
          img: 'static/logos/hosi.png',
          name: 'Homosexuelle Initiative (HOSI) Wien',
          type: 'lgbt',
          url: 'https://www.hosiwien.at/',
          statement: 'Ein demokratischer Staat sollte die bestehende Geschlechter&shy;vielfalt anerkennen und nicht bekämpfen. Ein freier und selbst&shy;bestimmter Geschlechts&shy;eintrag muss endlich möglich sein',
        },
        {
          img: 'static/logos/aidshilfe_salzburg.png',
          name: 'Aidshilfe Salzburg',
          type: 'aidshilfe_salzburg',
          url: 'https://www.aidshilfe-salzburg.at/',
        },
        {
          img: 'static/logos/psychotherapie_salzburg.png',
          name: 'Psychotherapie Salzburg - Florian Friedrich',
          type: 'psychotherapie_salzburg',
          url: 'https://www.psychotherapie-salzburg.de/',
        },
        {
          img: 'static/logos/bvg.png',
          name: 'BVG - Bundesvereinigung für Gendergerechtigkeit',
          type: 'bvg',
          url: 'https://gendergerechtigkeit.at/',
        },
        {
          img: 'static/logos/twospiritone.png',
          name: 'TWOspiritinONE',
          type: 'twospiritone',
          url: 'https://2spiritin1.at/',
        },
        {
          img: 'static/logos/hosi_tirol.png',
          name: 'HOSI Tirol',
          type: 'hosi_tirol',
          url: 'https://hositirol.at/',
        },
        {
          img: 'static/logos/plattform_intersex.png',
          name: 'Plattform Intersex',
          type: 'plattform_intersex',
          url: 'http://www.plattform-intersex.at/',
        },
        {
          img: 'static/logos/courage.png',
          name: 'Beratungsstelle COURAGE',
          type: 'courage',
          url: 'https://www.courage-beratung.at/',
        },
        {
          img: 'static/logos/lgbtq_htu.png',
          name: 'Queer Referat der HTU Wien',
          type: 'lgbtq_htu',
          url: 'https://htu.at/index.php/LGBT%2A',
        },
        {
          img: 'static/logos/piraten.png',
          name: 'Piratenpartei Österreichs',
          type: 'piraten',
          url: 'https://piratenpartei.at/',
        },
      ],
      partners: [
        {
          img: 'static/logos/venib.png',
          name: 'Venib - Verein Nicht-Binär',
          type: 'venib',
          url: 'https://venib.at/',
          description: 'Infrastruktur & Spenden&shy;abwicklung',
        },
        {
          img: 'static/logos/graupner.png',
          name: 'Dr. Helmut Graupner',
          type: 'graupner',
          url: 'https://www.graupner.at/',
          description: 'Rechtsanwalt',
        },
      ],
    };
  },
  methods: {
    shuffle(e) {
      if (e) e.preventDefault();

      this.$refs.supporter.shuffle();
    },
  },
  mounted() {
    this.shuffle();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.supporter {
  padding-bottom: 2rem;
}

.partners {
  margin-top: 2rem;
  padding-bottom: 2rem;
}

</style>
