<template>
  <div class="item">
    <transition-group :name="shuffleSpeed" tag="div" class="row align-items-center">
      <div class="col col-sup" v-for="item in items" v-bind:key="item.name">
        <!-- Card Flip -->
        <div class="card-flip" :title="item.name">
          <div class="flip">

            <div class="front">
              <!-- front content -->
                <a :href="item.url" target="_blank" :alt="item.name">
                  <span class="card" v-bind:class="item.type">
                    <img :src="item.img" class="card-img-top img-statement"
                    :alt="item.name" />
                  </span>
                </a>
            </div>

            <div class="back">
              <!-- back content -->
              <a :href="item.url" target="_blank" :alt="item.name">
                <span class="card" v-bind:class="item.type">
                  <h3 class="card-title text-center">{{item.name}}</h3>
                  <p v-if="item.description" class="text-center"
                  v-html="item.description"></p>
                </span>
              </a>
            </div>

          </div>
        </div>
      </div>
    </transition-group>
</div>
</template>

<script>

export default {
  name: 'FlipCards',
  props: ['items'],
  data() {
    return {
      publicPath: process.env.BASE_URL,
      shuffleSpeed: 'shuffleMedium',
    };
  },
  methods: {
    shuffle(e) {
      if (e) e.preventDefault();

      const arr = this.items.splice(0, 6);

      for (let i = arr.length - 1; i > 0; i -= 1) {
        const j = Math.floor(Math.random() * i);
        const temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
      }
      this.items.push(...arr);

      return false;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.shuffleMedium-move {
  transition: transform 1s;
}

.item {
  overflow: hidden;
  margin: 0 auto;
  padding-bottom: 2rem;
}

.item .col-sup {
  margin-top: 2rem;
}

.item .card {
  padding: 0.2rem;
  margin: 0 auto;
  text-align: left;
  width: 13rem;
  height: 9rem;
  border: 1px solid white;
  display: grid;
  align-content: center;
  justify-content: center;
}

.item .card .img-statement {
  max-width: 11rem;
  max-height: 8rem;
  width: auto;
  height: auto;
}

#content .item a {
  text-decoration: none;
  color: #181818;
}

#content .item a:not(:hover) {
  color: #181818;
  text-decoration: none;
}

.item .card:after {
  content: '';
  position: absolute;
  left: -3px;
  top: -3px;
  right: -3px;
  bottom: -3px;
  z-index: -1;
  opacity: 0.7;
  border-radius: 6px;
}

.item .rkl:after {
  background: linear-gradient(135deg, #181818 55%,
  #fdcd02 40%);
}

.item .vimoe:after {
  background: #500959;
}

.item .aidshilfe_salzburg:after {
  background: #f29400;
}

.item .bvg:after {
  background: #c68a15;
}

.item .hosi_tirol:after {
  background: #ff7000;
}

.item .piraten:after {
  background: #4c2582;
}

.item .psychotherapie_salzburg:after {
    background: linear-gradient(180deg, #186469 25%,
  #3b8e9d 25%, 50%, #74a4b2 50%, 75%, #bec6ca 75%);
}

.item .twospiritone:after {
    background: linear-gradient(180deg, #5bcefa 0%,
  #f7f6de 35%, 55%,#f1d7d5 65%, 75%, #4c3761 100%);
}

.item .plattform_intersex:after {
    background: linear-gradient(135deg, #009a00 0%,
  #0998d2 25%,#ffee15 50%, #b40d55 100%);
}

.item .lgbtq_htu:after {
    background: linear-gradient(180deg, #1e4f79 0%,
  #2376b6 50%,#599bd4 100%);
}

.item .courage:after  {
background: linear-gradient(180deg, #FE0000 0%,
#FD8C00 20%,
#FFE500 40%,
#119F0B 60%,
#0644B3 80%,
#C22EDC 100%);
}

/* http://barchok.com/flags.html */
.item .lgbt:after  {
background: linear-gradient(180deg, #FE0000 16.66%,
#FD8C00 16.66%, 33.32%,
#FFE500 33.32%, 49.98%,
#119F0B 49.98%, 66.64%,
#0644B3 66.64%, 83.3%,
#C22EDC 83.3%);
}

.item .nonbinary:after {
  background: linear-gradient(180deg, #FFF430 25%,
  #FFFFFF 25%, 50%, #9C59D1 50%, 75%, #181818 75%);
}

.item .transgender:after  {
  background: linear-gradient(180deg, #5BCEFA 20%,
  #F5A9B8 20%, 40%, #FFFFFF 40%, 60%, #F5A9B8 60%,
  80%, #5BCEFA 80%);
}

.item .genderqueer:after  {
  background: linear-gradient(180deg, #B57EDC 33.33%,
  #FFFFFF 33.33%, 66.66%, #4A8123 66.66%);
}

.item .genderfluid:after  {
  background: linear-gradient(180deg, #FF77A3 20%,
  #FFFFFF 20%, 40%, #BE18D6 40%, 60%, #181818 60%,
  80%, #333EBD 80%);
}

.item .agender:after  {
  background: linear-gradient(180deg, #181818 14.285%,
  #C3C3C3 14.285%, 28.57%, #FFFFFF 28.57%, 42.855%,
  #B8F483 42.855%, 57.14%, #FFFFFF 57.14%, 71.425%,
  #C3C3C3 71.425%, 85.71%, #181818 85.71%);
}

.partners .venib:after {
  background: linear-gradient(180deg, #FFF430 33%,
  #9C59D1 33%, 66%, #181818 66%);
}
.card-flip .back .card.venib {
  background-color:rgba(255, 255, 255, 0.7);
}

.partners .graupner:after  {
  background: linear-gradient(180deg, #191919 0%,
  #b4dfef 5%, 95%, #191919 100%);
}

.card-flip {
  perspective: 1000px;
  margin: 0 auto;
}

.card-flip:hover .flip,
.card-flip.hover .flip {
  transform: rotateY(180deg);
}

.card-flip,
.card-flip .front,
.card-flip .back {
  width: 13rem;
  height: 9rem;
}

.card-flip .flip {
  transition: 0.4s;
  transform-style: preserve-3d;
  position: relative;
}

.card-flip .front,
.card-flip .back {
  backface-visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
}

.card-flip .front {
  z-index: 2;
  transform: rotateY(0deg);
}

.card-flip .back {
  transform: rotateY(180deg);
}

.card-flip .back .card {
  background: none;
}

.partners {
  margin-top: 2rem;
  padding-bottom: 2rem;
}

</style>
