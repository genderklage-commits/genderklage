<template>
  <div class="accordion" role="tablist">
    <div v-for="(entry, index) in entries" v-bind:key="index">
      <b-card no-body class="mb-1" :id="'accordion-' + id + index + '-card'">
        <b-card-header header-tag="header" class="p-1" role="tab">
          <b-button block v-b-toggle="'accordion-' + id + index"
          :id="'accordion-' + id + index + '-btn'">
            {{entry.title}}
          </b-button>
        </b-card-header>
        <b-collapse :id="'accordion-' + id + index"
        @shown="handleClick('accordion-' + id + index)"
          accordion="my-accordion" role="tabpanel">
          <b-card-body>
            <b-card-text v-html="entry.text"
             data-track-content data-content-name="FAQ"
            :data-content-piece="id + index + ' - ' + entry.title"></b-card-text>
          </b-card-body>
        </b-collapse>
      </b-card>
    </div>
  </div>
</template>

<script>
/* eslint-disable global-require */

export default {
  name: 'accordion',
  props: ['id', 'entries'],
  methods: {
    handleClick(id) {
      const elCard = document.getElementById(`${id}-card`);
      const elBtn = document.getElementById(`${id}-btn`);
      const isBtnVisible = this.isElementInViewport(elBtn);
      const isCardVisible = this.isElementInViewport(elCard);
      const isCardTaller = this.isElementTallerThanViewport(elCard);

      if (!isCardVisible) {
        elCard.scrollIntoView({ block: (isCardTaller || !isBtnVisible) ? 'start' : 'end', behavior: 'smooth' });
      }
    },
    isElementInViewport(el) {
      const rect = el.getBoundingClientRect();
      return (
        rect.top >= 0
        && rect.left >= 0
        && rect.bottom <= (window.innerHeight || document.documentElement.clientHeight)
        && rect.right <= (window.innerWidth
        || document.documentElement.clientWidth)
      );
    },
    isElementTallerThanViewport(el) {
      return (el.offsetHeight > (window.innerHeight || document.documentElement.clientHeight));
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.btn-secondary {
    border: none;
    text-align: left;
}

.btn-secondary:not(:hover):not(:focus) {
    background-color: #e9ecef;
    color: #181818;
}

.btn-secondary:hover, .btn-secondary:focus {
    outline:none;
    box-shadow:none;
}

p.card-text {
  text-align: left;
}

</style>
