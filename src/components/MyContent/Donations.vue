<template>
  <div>
    <h2 id="Donations" data-track-content data-content-name="Content"
    data-content-piece="Donations">
    Mitfinanzieren</h2>
    <p>Der Weg vor Gericht ist lange und kostspielig und
      die Erkenntnisse des VfGH kommen in der einen
      oder anderen Form allen Menschen zu Gute, weil die aktuelle Regelung gekippt und
      verbessert wird oder falls die Klage keinen Erfolg hat, die Begründung genutzt werden
      kann, um es von einer anderen Richtung kommend weiter zu versuchen. Auf die neuen
      Regelungen können sich, sobald sie umgesetzt sind, jedenfalls alle berufen.
    </p>
    <div class="donateprogressbar progress">
      <div class="progress-bar progress-bar-striped progress-bar-animated" :style="don_style" >
      {{don_header}}
      </div>
      <div class="spent-bar progress-bar-striped progress-bar-animated" :style="spent_style">
      </div>
    </div><div class="float-right" style="margin-top: -2rem;">
      <small>{{don_state}}</small></div>
    <p>Wir freuen uns über jede Spende! Falls du auf einen Wink vom Schicksal gewartet hast,
    hier ist er ;)
    </p>
    <!--<div><h3>Banküberweisung</h3></div>-->
    <b-container class="bankdetails container-fluid">
      <b-row>
        <b-col md="12">
          <b-row class="align-items-center">
            <b-col md="9">
              <b-row>
                <b-col md="4"><label for="input_name">Zahlungsempfänger</label></b-col>
                <b-col><MyCopyField title="name" :text="name" variant="purple"
                alt="Zahlungsempfänger in die Zwischenablage kopieren" /></b-col>
              </b-row>
              <b-row>
                <b-col md="4"><label for="input_iban">IBAN</label></b-col>
                <b-col><MyCopyField title="iban" :text="iban" variant="purple"
                alt="IBAN in die Zwischenablage kopieren" /></b-col>
              </b-row>
              <b-row>
                <b-col md="4"><label for="input_reason">Verwendungszweck</label></b-col>
                <b-col><MyCopyField title="reason" :text="reason" variant="purple"
                alt="Verwendungszweck in die Zwischenablage kopieren" /></b-col>
              </b-row>
            </b-col>
            <b-col md="2" class="text-center">
              <b-row class="bankdetails_qr">
                <b-col md="auto">
                  <canvas ref="qrCodeContainer"
                  alt="QR-Code mit der Banking App scannen"
                  title="QR-Code mit der Banking App scannen"></canvas>
                </b-col>
              </b-row>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </b-container>
    <!--<div>
      <b-row>
        <b-col md="9"><h3>PayPal</h3>
        </b-col>
        <b-col class="text-center" md="2" style="margin-left: 7.5px;">
          <a target="_blank" href="">
            <img src="../../../public/static/paypal.webp" title="Mit PayPal beteiligen"
            width="116px" height="32px" />
          </a>
        </b-col>
      </b-row>
    </div>-->
    <br />
    <p>Organisationen und Personen, die gerne namentlich erwähnt werden möchten, schreiben bitte
      den Namen, mit dem sie aufscheinen wollen in den Verwendungszweck
      (z.B. "{{reason}} - Name"), ansonsten scheint die Spende als "Anonym" auf:
      <a target="_blank" rel="noopener"
      href="https://blog.genderklage.at/spenden/">
      Liste der Spenden</a>.
    </p>
    <p>Einnahmen und Ausgaben sind transparent einsehbar:
      <a target="_blank" rel="noopener"
      href="https://blog.genderklage.at/kostenuebersicht/">
      Kostenübersicht</a>.
    </p>
    <p>Spenden ohne Verwendungszweck werden für die allgemeine
      Vereinstätigkeit bei Venib benutzt.</p>

    <div class="donors">
    <h3>Spender*innen</h3>
    <p>{{don_donors}}</p>
    <small>Reihenfolge nach Spendenzeitpunkt</small>
    </div>
  </div>
</template>

<script>
import MyCopyField from './MyCopyField.vue';

const ibanQrCode = require('iban-qr-code');
const QRious = require('qrious');

export default {
  name: 'Donations',
  data() {
    return {
      name: 'Venib',
      iban: 'AT022011184424937200',
      reason: 'Spende für Genderklage',
      don_header: 'lade daten...',
      don_state: 'lade daten...',
      don_style: { width: '0%' },
      spent_style: { width: '0%' },
      don_donors: 'lade daten...',
    };
  },
  components: {
    MyCopyField,
  },
  mounted() {
    const qrCodeString = ibanQrCode.girocode({
      name: this.name,
      iban: this.iban,
      bic: 'GIBAATWWXXX',
      currency: 'EUR',
      amount: '0.00',
      char: '', // Purpose of the Credit Transfer (AT-44)
      ref: '', // ISO 11649 RF Creditor Reference may be used here
      reason: this.reason,
      hint: '', // note to user,
      version: '002', // Version of Quick Response Code 001 or 002
    });

    const qrGiroCode = new QRious({
      element: this.$refs.qrCodeContainer,
    });

    qrGiroCode.set({
      background: 'white',
      foreground: 'black',
      padding: 25,
      size: 200,
      level: 'H',
      value: qrCodeString,
    });

    this.fetchDonationState();
    this.fetchDonors();
  },
  methods: {
    async fetchDonationState() {
      try {
        this.isLoading = true;
        const res = await this.$http({
          method: 'get',
          url: 'https://blog.genderklage.at/wp-json/api/v1/donations',
          dataType: 'json',
        });

        const data = JSON.parse(JSON.stringify(res.data));
        this.don_header = `Spenden: ${data.Spenden} von ${data.Ausgaben} EUR`;
        this.don_state = `Bisherige Ausgaben: ${data.Ausgaben} EUR, Saldo: ${data.Saldo} EUR, Stand: ${data.Covered}. Finanzierungsziel: ${data.Ziel}, Stand: ${data.Fortschritt}`;
        this.don_style.width = data.Fortschritt;
        this.spent_style.width = data.Gap;
      } catch (err) {
        console.log(err);
      } finally {
        this.isLoading = false;
      }
    },
    async fetchDonors() {
      try {
        this.isLoading = true;
        const res = await this.$http({
          method: 'get',
          url: 'https://blog.genderklage.at/wp-json/api/v1/donors',
          dataType: 'json',
        });

        const data = JSON.parse(JSON.stringify(res.data));
        this.don_donors = `${data.join(', ')} & zahlreiche anonyme Personen`;
      // eslint-disable-next-line no-empty
      } catch (err) {
        console.log(err);
      } finally {
        this.isLoading = false;
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.donateprogressbar {
  height: 3rem;
  font-size: 1rem;
  margin-top: 2rem;
  margin-bottom: 2rem;
  text-align: left;
}

.donateprogressbar .progress-bar{
  background-color: #63a62e;
  overflow: visible;
  padding-left: 1rem;
  font-weight: bold;
  color: #181818;
  z-index: 2;
}

.spent-bar {
  background-color: #9C59D1;
  z-index: 1;
  transition: 3s ease;
}

@media (min-width: 9000px) {
  .donateprogressbar .progress-bar {
    color: #FFFFFF;
  }
}

.bankdetails {
  text-align: left;
}

.bankdetails .col-sm-4 {
  min-width: 4rem;
}

.form-control:focus {
    color: #495057;
    background-color: #fff;
    border-color: #80bdff;
    outline: 0;
    box-shadow: 0 0 0 0.2rem rgb(0 123 255 / 25%);
}

.donors {
  margin-top: 2rem;
}

.donors p {
  text-align: center;
  font-style: italic;
}

</style>
