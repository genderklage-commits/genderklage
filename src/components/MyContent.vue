<template>
  <div>
    <main role="main" class="container">
      <Intro />
      <Roadmap />
      <Donations />
      <Supporters />
      <Participate />
      <FAQ />
    </main>
  </div>
</template>

<script>
import Intro from './MyContent/Intro.vue';
import Roadmap from './MyContent/Roadmap.vue';
import Donations from './MyContent/Donations.vue';
import Supporters from './MyContent/Supporters.vue';
import Participate from './MyContent/Participate.vue';
import FAQ from './MyContent/FAQ.vue';

export default {
  name: 'MyContent',
  components: {
    Intro,
    Roadmap,
    Donations,
    Supporters,
    Participate,
    FAQ,
  },
};
</script>
