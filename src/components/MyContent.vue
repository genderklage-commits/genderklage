<template>
  <div>
    <main role="main" class="container">
      <Intro v-if="show"/>
      <Roadmap v-if="show"/>
      <Donations v-if="show"/>
      <Supporters v-if="show"/>
      <Participate v-if="show"/>
      <FAQ />
    </main>
  </div>
</template>

<script>

const Intro = () => import('./MyContent/Intro.vue');
const Roadmap = () => import('./MyContent/Roadmap.vue');
const Donations = () => import('./MyContent/Donations.vue');
const Supporters = () => import('./MyContent/Supporters.vue');
const Participate = () => import('./MyContent/Participate.vue');
const FAQ = () => import('./MyContent/FAQ.vue');

export default {
  name: 'MyContent',
  data() {
    return {
      show: false,
    };
  },
  mounted() {
    this.show = true;
  },
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
