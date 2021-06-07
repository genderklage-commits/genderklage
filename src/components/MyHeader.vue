<template>
  <div class="masthead-container">
    <header class="masthead">
    <div class="container h-100">
      <div class="row h-100 align-items-center">
        <div class="col-12 text-left header-box">
          <div class="header-box-typer">
            <transition name="slide-fade" mode="out-in">
              <span :key="show" class="h1 font-weight-bolder"
              v-html="statements[show]"></span>
            </transition>
          </div>
          <div class="header-box-text">
          <h1 class="slogan">Wir klagen die An&shy;erkennung der individuellen
          Geschlechts&shy;identität ein.</h1>
          </div>
        </div>
      </div>
     </div>
    </header>
  </div>
</template>

<script>

export default {
  name: 'MyHeader',
  data() {
    return {
      show: 0,
      statements: [
        'genderklage.at',
        'Die Geschlechts&shy;identität ist individuell.',
        'Selbst&shy;bestimmung ist ein Menschen&shy;recht.',
        'Die staatliche An&shy;erkennung ist überfällig.',
      ],
    };
  },
  methods: {
    nextSlogan() {
      this.show = (this.show + 1) % this.statements.length;
    },
  },
  mounted() {
    this.show = 1;
    this.statements.shift();

    setInterval(() => {
      this.nextSlogan();
    }, 6000);
  },
};
</script>

<style scoped>

.slide-fade-enter-active {
  transition: all 1.5s ease;
}
.slide-fade-leave-active {
  transition: all 1.5s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}

.header-box-text {
  margin-top: 0.6rem;
  margin-bottom: 2rem;
}

.slogan {
  text-shadow: 0px 0px 8px white;
  font-size: 1.5rem;
  line-height: 1.5;
  margin-bottom: 0;
}

header {
  border-bottom: 2px solid #181818;
}

.masthead-container{
  min-height: 100vh;
  background-image: url('../../public/static/header_min.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.masthead {
  min-height: 100vh;
  background-image: url('../../public/static/header_4k.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

@media (max-width: 1000px) and (max-height: 667px)
{
  .masthead {
    background-image: url('../../public/static/header_1k.jpg');
  }
}
@media (max-width: 1920px) and (max-height: 1280px)
{
  .masthead {
    background-image: url('../../public/static/header_2k.jpg');
  }
}

.masthead {
  font-size: 1.5rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding-bottom: 16vh;
}

.masthead p {
  max-width: 40rem;
}

.header-box {
  position: relative;
  padding-left: 1.5em;
}

.header-box:before {
  content: "";
  position: absolute;
  width: 0.4em;
  height: 100%;
  left: 0.5em;
  top: 0;
  background: linear-gradient(180deg, #FFF430 25%, #FFFFFF 25%, 50%,
  #9C59D1 50%, 75%, #181818 75%);
}

@media (min-width: 991px) and (max-width: 1500px)
{
  .masthead .slogan {
    max-width: 50%;
  }
}

@media (min-width: 555px) and (max-width: 991px)
{
  .masthead {
    padding-bottom: 9vh;
  }

  .header-box-typer {
    min-height: 108px;
    max-width: 95%;
  }
}

@media (max-width: 555px)
{
  .masthead {
    padding-bottom: 8vh;
  }

  .masthead .slogan {
    max-width: 85%;
  }

  .header-box-typer {
    min-height: 147px;
    max-width: 95%;
  }
}

</style>
