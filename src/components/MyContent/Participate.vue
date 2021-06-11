<template>
  <div>
    <h2 id="Participate"
    data-track-content data-content-name="Content" data-content-piece="Participate">
      Mitmachen &amp; auf dem Laufenden bleiben</h2>
    <b-container class="social_media_container">
      <b-row align-h="center">
         <b-col cols="1"><a target="_blank" class="facebook"
          href="https://www.facebook.com/genderklage" rel="noopener">
            <img src="../../../public/static/icons/Facebook.png"
            widht="32" height="32" title="Facebook" alt="Facbeook"/></a>
          </b-col>
          <b-col cols="1"><a target="_blank" class="twitter"
          href="https://twitter.com/genderklage" rel="noopener">
            <img src="../../../public/static/icons/Twitter.png"
            widht="32" height="32" title="Twitter" alt="Twitter"/></a>
          </b-col>
          <b-col cols="1"><a target="_blank" class="instagram"
          href="https://www.instagram.com/genderklage/" rel="noopener">
            <img src="../../../public/static/icons/Instagram.png"
            widht="32" height="32" title="Instagram" alt="Instagram"/></a>
          </b-col>
          <b-col cols="1"><a target="_blank" class="tiktok"
          href="https://www.tiktok.com/@genderklage" rel="noopener">
            <img src="../../../public/static/icons/TikTok.png"
            widht="32" height="32" title="TikTok" alt="TikTok"/></a>
          </b-col>
      </b-row>
    </b-container>

    <h3>Newsletter</h3>
    <p>Updates posten wir auf unserem
    <a href="https://blog.genderklage.at/" target="_blank" rel="noopener">Blog</a>, der per
    <a href="https://blog.genderklage.at/newsletter" target="_blank" rel="noopener">E-Mail</a>
    oder
    <a href="https://blog.genderklage.at/feed" target="_blank" rel="noopener">RSS</a>
    abonniert werden kann. Du kannst dich hier für den Newsletter eintragen:</p>
    <div class="newsletter">
      <b-form @submit="onSubmit" v-if="show">
        <div class="input-group">
          <b-form-input
            id="email"
            v-model="form.email"
            type="email"
            placeholder="E-Mail Adresse"
            required
          ></b-form-input>
          <div class="input-group-append">
            <b-button type="submit" variant="purple"
            title="zum Newsletter anmelden" alt="zum Newsletter anmelden">
            anmelden</b-button>
          </div>
        </div>
      </b-form>
      <div class="newsletterstatus">
      <p class="message" v-html="message"></p>
      <p class="errormsg" v-html="errormsg"></p>
      <div class="dotscontainer" v-if="isLoading">
      <div id="dots3">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
      </div></div>
      </div>
    </div>

    <h3>Telegram</h3>
    <p>Wer sich gerne zu diesem Thema vernetzen möchte, kann der Telegram Gruppe
      beitreten. Die Gruppe ist öffentlich, um
      einen niederschwelligen Zugang zu ermöglichen. Bitte seid respektvoll!
    </p><a href="https://t.me/genderklage" target="_blank" rel="noopener" class="callout_a">
    <div class="callout">
      <div class="callout_content">
        <img src="../../../public/static/telegram.png"
        alt="Telegram Logo" />
        <span>https://t.me/genderklage</span>
      </div>
    </div></a>
    <p>
    Bei Interesse einen gleich oder ähnlich lautenden Antrag zu stellen,
    würden wir uns über eine Zusammenarbeit jedenfalls freuen. Gerne per
    Telegram melden oder an die E-Mail-Adresse im Impressum schreiben!
    </p>
  </div>
</template>

<script>

export default {
  name: 'Participate',
  data() {
    return {
      form: {
        email: '',
      },
      show: true,
      message: '&nbsp;',
      errormsg: '',
      isLoading: false,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      if (event?.srcElement) event.srcElement.blur();
      this.message = '&nbsp;';
      this.errormsg = '';

      if (this.validateEmail(this.form.email)) {
        this.$matomo.trackEvent('click', 'Newsletter');
        this.subscribeToNewsletter(this.form.email);
      } else {
        this.errormsg = 'Bitte gib eine gültige E-Mail-Adresse ein!';
        this.message = '';
      }
    },
    validateEmail(email) {
      // eslint-disable-next-line no-useless-escape
      const re = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
    async subscribeToNewsletter(email) {
      try {
        this.isLoading = true;
        const res = await this.$http({
          method: 'post',
          url: 'https://blog.genderklage.at/wp-json/api/v1/newsletter',
          // eslint-disable-next-line object-shorthand
          data: { email: email },
          dataType: 'json',
        });
        if (res.data.error === false) {
          this.message = 'Bitte bestätige die Anmeldung mit dem Link den wir dir gerade geschickt haben!';
        } else {
          this.message = '';
          this.errormsg = `${res.data.msg}. Bitte melde dich hier an: <a href="https://blog.genderklage.at/newsletter" target="_blank">Zum Newsletter anmelden</a>`;
        }
      } catch (err) {
        this.message = '';
        this.errormsg = 'Unbekannter Fehler. Bitte melde dich hier an: <a href="https://blog.genderklage.at/newsletter" target="_blank">Zum Newsletter anmelden</a>';
      } finally {
        this.isLoading = false;
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

h3, .h3 {
  text-align: left;
  margin-top: 2rem;
}

.callout {
  margin: 0 auto;
  margin-top: 2rem;
  margin-bottom: 2rem;
  border: 1px solid #eee;
  border-radius: 3px;
}

.callout_a {
  text-decoration: none;
  color: #0d6efd;
}

.callout_a:hover{
  color: white;
}

.callout:hover {
  background-color: #0088cc;
}

.callout img {
  height: 2rem;
  margin-right: 1rem;
}

.callout_content
{
  margin: 0.5rem;
  word-break: break-word;
}

.social_media_container {
    padding: 3rem;
}

.social_media_container .col-1 {
  min-width: 62px;
}

.social_media_container a  {
  padding: 14px 12px 19px 12px;
  background-color: #eee;
}

.social_media_container a.facebook:hover  {
  background-color: #3b5998;
}
.social_media_container a.twitter:hover  {
  background-color: #1DA1F2;
}
.social_media_container a.instagram:hover  {
  background-color: #E1306C;
}
.social_media_container a.tiktok:hover  {
  background-color: #000;
}

.social_media_container a:hover img {
  filter: invert(100%) brightness(400%);
}

.social_media_container a:active img {
  filter: invert(88%) sepia(33%) saturate(5945%) hue-rotate(354deg) brightness(107%) contrast(101%);
}

.social_media_container a:focus img {
  filter: invert(27%) sepia(81%) saturate(1780%) hue-rotate(245deg) brightness(82%) contrast(88%);
}

.newsletterstatus {
  min-height: 1.2rem;
}

.message {
  font-size: small;
  color: #6f42c1;
}
.errormsg {
  font-size: small;
  color: #ffc107;
}

.dotscontainer {
  position: relative;
  top: 2rem;
}

/**===== dots3 =====*/
#dots3 {
  display: block;
  position: absolute;
  left: 50%;
  height: 50px;
  width: 50px;
  margin: -25px 0 0 -25px;
}

#dots3 span {
  position: absolute;
  width: 10px;
  height: 10px;
  background: rgba(0, 0, 0, 0.25);
  border-radius: 50%;
  -webkit-animation: dots3 1.5s infinite ease-out;
          animation: dots3 1.5s infinite ease-out;
}

#dots3 span:nth-child(1) {
  left: 0px;
  -webkit-animation-delay: 0.2s;
          animation-delay: 0.2s;
}

#dots3 span:nth-child(2) {
  left: 15px;
  -webkit-animation-delay: 0.4s;
          animation-delay: 0.4s;
}

#dots3 span:nth-child(3) {
  left: 30px;
  -webkit-animation-delay: 0.6s;
          animation-delay: 0.6s;
}

#dots3 span:nth-child(4) {
  left: 45px;
  -webkit-animation-delay: 0.8s;
          animation-delay: 0.8s;
}

@keyframes dots3 {
  0% {
    background: #000000;
    -webkit-transform: scale(0.1);
            transform: scale(0.1);
    -webkit-transform: scale(0.1);
            transform: scale(0.1);
  }
  50% {
    background: rgba(0, 0, 0, 0.25);
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
  }
  100% {
    background: #000000;
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-transform: scale(1);
            transform: scale(1);
  }
}
@-webkit-keyframes dots3 {
  0% {
    background: #000000;
    -webkit-transform: scale(0.1);
            transform: scale(0.1);
  }
  50% {
    background: rgba(0, 0, 0, 0.25);
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
  }
  100% {
    background: #000000;
    -webkit-transform: scale(1);
            transform: scale(1);
  }
}
/** END of dots3 */

</style>
