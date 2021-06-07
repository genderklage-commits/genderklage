<template>
  <div class="input-group mb-3">
    <input ref="data_text" readonly="readonly"
    type="text" class="form-control" aria-describedby="basic-addon2"
    form-control-static :value="text" />
    <div class="input-group-append">
      <button :class="'btn btn-' + variant" type="button" @click="copy_data"
      :alt="alt" :title="alt">
        <svg v-if="!data_copied"
          xmlns="http://www.w3.org/2000/svg" width="16" height="16"
          fill="currentColor" class="bi bi-clipboard" viewBox="0 0 16 16">
          <path d="M4 1.5H3a2 2 0 0 0-2 2V14a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3.5a2 2
          0 0 0-2-2h-1v1h1a1 1 0 0 1 1 1V14a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V3.5a1 1 0
          0 1 1-1h1v-1z"/>
          <path d="M9.5 1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-3a.5.5 0 0
          1-.5-.5v-1a.5.5 0 0 1 .5-.5h3zm-3-1A1.5 1.5 0 0 0 5 1.5v1A1.5
          1.5 0 0 0 6.5 4h3A1.5 1.5 0 0 0 11 2.5v-1A1.5 1.5 0 0 0 9.5 0h-3z"/>
        </svg>
        <svg v-if="data_copied"
          xmlns="http://www.w3.org/2000/svg" width="16" height="16"
          fill="currentColor" class="bi bi-clipboard-check" viewBox="0 0 16 16">
          <path fill-rule="evenodd" d="M10.854 7.146a.5.5 0 0 1 0 .708l-3 3a.5.5
            0 0 1-.708 0l-1.5-1.5a.5.5 0 1 1 .708-.708L7.5 9.793l2.646-2.647a.5.5
            0 0 1 .708 0z"/>
          <path d="M4 1.5H3a2 2 0 0 0-2 2V14a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3.5a2
            2 0 0 0-2-2h-1v1h1a1 1 0 0 1 1 1V14a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V3.5a1
            1 0 0 1 1-1h1v-1z"/>
          <path d="M9.5 1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-3a.5.5 0 0
            1-.5-.5v-1a.5.5 0 0 1 .5-.5h3zm-3-1A1.5 1.5 0 0 0 5 1.5v1A1.5
            1.5 0 0 0 6.5 4h3A1.5 1.5 0 0 0 11 2.5v-1A1.5 1.5 0 0 0 9.5 0h-3z"/>
        </svg>
      </button>
    </div>
  </div>
</template>

<script>
import Vue from 'vue';
import VueClipboard from 'vue-clipboard2';

Vue.use(VueClipboard);

export default {
  props: ['title', 'text', 'alt', 'variant'],
  data() {
    return {
      data_copied: false,
    };
  },
  methods: {
    copy_data(e) {
      if (e) e.preventDefault();

      this.$copyText(this.text).then(() => {
        const selection = window.getSelection();
        this.data_copied = true;

        if (selection.rangeCount > 0) {
          selection.removeAllRanges();
        }

        const range = document.createRange();
        range.selectNodeContents(this.$refs.data_text);
        selection.addRange(range);

        setTimeout(() => {
          this.data_copied = false;
          selection.removeAllRanges();
        }, 150);

        this.$matomo.trackEvent('click', 'CopyData', this.title);
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.form-control[readonly] {
  background-color: white;
}

</style>
