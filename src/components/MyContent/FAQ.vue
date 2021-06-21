<template>
  <div>
    <h2 id="FAQ"
    data-track-content data-content-name="Content" data-content-piece="FAQ">FAQ</h2>
    <h3>Zur Geschlechtsidentität</h3>
    <MyAccordion id="1" :entries="faqgeneral" />
    <h3>Zur Klage</h3>
    <MyAccordion id="2" :entries="faqklage" />
    <h3>Zum Spenden</h3>
    <MyAccordion id="3" :entries="faqdonations" />
    <h3>Zur Webseite</h3>
    <MyAccordion id="4" :entries="faqwebsite" />
  </div>
</template>

<script>
/* eslint-disable global-require */
import MyAccordion from './MyAccordion.vue';

export default {
  name: 'FAQ',
  components: {
    MyAccordion,
  },
  data() {
    return {
      faqgeneral: [
        {
          // eslint-disable-next-line no-multi-str
          title: 'Was ist eine Geschlechtsidentität? Warum nicht einfach Geschlecht? ', text: '\
          <p>Im wissenschaftlichen Sprachgebrauch wird "gender" als Bezeichnung für das soziale Geschlecht\
          und in Abgrenzung dazu "sex" als biologisches Geschlecht definiert.\
          Es gibt viel mehr als nur zwei Geschlechtsidentitäten! Nicht alle Menschen sind Männer oder\
          Frauen. Diese Personen bezeichnen sich zum Beispiel als nicht-binär oder genderqueer.\
          Auch auf körperlicher Ebene lassen sich Menschen nicht in zwei Geschlechterschubladen\
          einteilen (siehe inter).</p><br />\
          <a target="_blank" rel="noopener" href="https://genderdings.de/gender/geschlechtsidentitaet/">https://genderdings.de/gender/geschlechtsidentitaet/</a><br/>\
          <a target="_blank" rel="noopener" href="https://www.uni-bielefeld.de/gendertexte/gender.html">https://www.uni-bielefeld.de/gendertexte/gender.html</a>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Was bedeutet inter?', text: '\
          <p>Menschen werden bei oder schon vor der Geburt anhand ihrer Genitalien einem Geschlecht zugeordnet\
          – meistens männlich oder weiblich. Eigentlich sind für körperliche Geschlechtsmerkmale aber nicht nur\
          die Genitalien relevant, sondern noch mindestens drei weitere Ebenen:</p>\
          <ul><li>Chromosomen: XX gilt als weiblich, XY gilt als männlich.</li>\
          <li>Hormone: überwiegend Östrogen und Progesteron gelten als weiblich, überwiegend Testosteron gilt als männlich.</li>\
          <li>Keimdrüsen: Eierstöcke gelten als weiblich, Hoden gelten als männlich.</li>\
          <li>Genitalien: Vulva und Vagina gelten als weiblich, Penis gilt als männlich.</li></ul>\
          <p>Ein Mensch mit XX-Chromosomen, Vagina, Eierstöcken und überwiegend Östrogen gilt als weiblich.\
          Ein Mensch mit XY-Chromosomen, Penis, Hoden und überwiegend Testosteron gilt als männlich. Sind bei\
          einem Menschen manche dieser Ebenen männlich und andere weiblich, oder andersherum, gilt er\
          medizinisch als „intersexuell“. Inter Menschen werden also mit Variationen der körperlichen\
          Geschlechtsmerkmale geboren.</p>\
          <p>„Intersexuell“ ist ein medizinisches Wort und wird deshalb von vielen Menschen abgelehnt.</p>\
          <br />\
          <a target="_blank" rel="noopener" href="https://vimoe.at/ueber-inter/">https://vimoe.at/ueber-inter/</a><br/>\
          <a target="_blank" rel="noopener" href="https://genderdings.de/koerper/intergeschlechtlichkeit/">https://genderdings.de/koerper/intergeschlechtlichkeit/</a>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Was bedeutet trans?', text: '\
          <p>Bei vielen Menschen stimmt die Geschlechtsidentität mit dem Geschlecht überein,\
          das ihnen bei Geburt zugewiesen wurde – sie sind cisgeschlechtlich, kurz cis. Aber\
          nicht alle Menschen können oder wollen in dem Geschlecht leben, dem sie bei ihrer\
          Geburt aufgrund körperlicher Merkmale zugeordnet wurden. Diese Menschen sind\
          transgeschlechtlich oder trans*.</p><br />\
          <p>Trans* Menschen wissen, ebenso wie cis Menschen, selbst am besten, welche\
          Geschlechtsidentität sie haben. Trans* Männer sind Männer und trans* Frauen\
          sind Frauen – genau wie cis Männer und cis Frauen. Dafür ist es nicht wichtig,\
          wie ihre Geschlechtsorgane aussehen und ob sie sich für oder gegen\
          geschlechtsangleichende medizinische Maßnahmen entscheiden.</p>\
          <br />\
          <a target="_blank" rel="noopener" href="https://www.transx.at/Pub/TransWas.php">https://www.transx.at/Pub/TransWas.php</a><br/>\
          <a target="_blank" rel="noopener" href="https://genderdings.de/gender/geschlechtsidentitaet/">https://genderdings.de/gender/geschlechtsidentitaet/</a>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0, title: 'Was bedeutet die Diagnosse Transsexualität?', text: '\
          <p>Die Weltgesundheitsorganisation (WHO) hat am 18.06.2018 ihren grundlegend überarbeiteten\
          Krankheitenkatalog ICD-11 vorgestellt. Eine wichtige Neuerung: Trans* Personen werden nicht\
          länger als Menschen mit „Störungen der Geschlechtsidentität“ im Abschnitt „Mentale und\
          Verhaltensstörungen“ eingeordnet.</p>\
          <p>Stattdessen findet sich im neuen Abschnitt „Conditions related to sexual health“\
          (auf Deutsch etwa: mit der sexuellen Gesundheit zusammenhängende Umstände) die Kategorie\
          „Gender incongruence“.</p>\
          <p>Definiert wird diese „Geschlechts-Inkongruenz” als ausgeprägte und beständige Nichtübereinstimmung\
          zwischen dem erlebten und dem bei der Geburt zugewiesenen Geschlecht.\
          Die bisherige Diagnose als psychisch und verhaltensgestört habe maßgeblich zu Stigmatisierung und\
          gesellschaftlicher Marginalisierung von trans* Menschen beigetragen.<p>\
          <p>In Kraft treten soll das neue Verzeichnis dann am 1. Januar 2022.</p>\
          <a target="_blank" rel="noopener" href="https://www.aidshilfe.de/meldung/icd-11">https://www.aidshilfe.de/meldung/icd-11</a><br/>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0, title: 'Was ist der Unterschied zwischen Transsexualität und Geschlechts-Inkongruenz?', text: '\
          <p>In der Vergangenheit wurde die trans Identität pathologisiert, also trans zu sein als etwas Krankhaftes\
          dargestellt.\
          Durch die neue Definition ist das nicht mehr der Fall, stattdessen beschreibt die Diagnose \
          die fehlende Übereinstimmung zwischen erlebtem und aufgrund äußerer Geschlechtsmerkmale zugewiesenem Geschlecht,\
          d.h. es wird nur das pathologisiert, was auch behandelt werden kann, wenn die Betroffenen das möchten \
          (z.B. durch Psychotherapie oder geschlechtsangleichende Maßnahmen).</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0, title: 'Ist es nicht sinnvoll, dass der Staat prüft ob Kritieren für einen Personstandswechsel vorliegen?', text: '\
          <p>Nicht alle benötigen eine medizinische Behandlung und\
          nicht alle die eine brauchen, wollen jeden dieser Schritte gehen. Die Erkenntnis,\
          dass es unterschiedliche Bedürfnisse gibt, und dass auf die individuellen Wünsche einzugehen ist, um den Erfolg der\
          Behandlung nicht zu gefährden, setzt sich auch unter den behandelnden Ärztinnen und Therapeutinnen durch.</p>\
          <a target="_blank" rel="noopener" href="https://www.transx.at/Pub/Medizinisches.php">https://www.transx.at/Pub/Medizinisches.php</a><br/>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0, title: 'Was bedeutet nichtbinär, genderqueer und exgender?', text: '\
          <p>Nichtbinär, abinär, non-binär/nonbinary und genderqueer werden oft mit derselben Bedeutung verwendet,\
          nämlich: Ein Geschlecht, das weder ganz/immer weiblich ist, noch ganz/immer männlich. Damit sind sie Überbegriffe\
          für sehr verschiedene Arten, das eigene Geschlecht zu erleben.</p>\
          <p>Manche Menschen erleben ihr Geschlecht in keiner Relation zu Männlichkeit oder Weiblichkeit, für manche gibt es nicht ein\
          Geschlecht, das immer gleich bleibt, sondern ihr Geschlecht verändert sich ab und zu, manche haben mehr als ein Geschlecht\
          oder Nicht-Geschlecht, manche können kein Gefühl von Geschlecht in sich entdecken oder sind eben einfach sie selbst,\
          manche haben überhaupt keine Lust, sich und ihr Erleben oder Nicht-Erleben von Geschlecht als männlich, weiblich oder\
          irgend etwas anderes zu benennen. Andere lehnen diese Begriffe überhaupt ab, da sie sie lediglich als weitere ungefragte\
          Kategorisierungen verstehen, oder die Verwendung von „binär“ und „nichtbinär“ als Gegensatzpaar ablehnen.\
          Einige davon verstehen sich einfach als queer, trans oder trans* andere lehnen auch diese Bezeichnungen ab.</p>\
          <p>Exgender (auch egender) is eine spezifischere Bezeichnung für Menschen, die eine Einordnung innerhalb\
          bzw. um das Gender-Spektrum und Gender-Kategorien grundsätzlich ablehnen. </p>\
          <p>Manchmal werden diese spezifischen Geschlechter genauer benannt, manchmal einfach nur der Überbegriff dafür verwendet.\
          Nicht alle Menschen, auf die diese Definitionen zutreffen, verstehen sich tatsächlich als nichtbinär/abinär oder genderqueer.</p>\
          <a target="_blank" rel="noopener" href="https://nibi.space/nichtbin%C3%A4r_und_genderqueer">https://nibi.space/nichtbinär_und_genderqueer</a><br/>\
          <a target="_blank" rel="noopener" href="https://www.transx.at/Pub/TransWas.php">https://www.transx.at/Pub/TransWas.php</a><br />\
          <a target="_blank" rel="noopener" href="https://www.queerundefined.com/search/egender/exgender">https://www.queerundefined.com/search/egender/exgender</a> (en)\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0, title: 'Was bedeutet Queer?', text: '\
          <p>Queer ist ein Sammelbegriff für Personen, deren geschlechtliche Identität und/oder sexuelle Orientierung (wen\
          sie begehren oder wie sie lieben) nicht der <a target="_blank" rel="noopener" \
          href="https://diversity-arts-culture.berlin/woerterbuch/heteronormativitaet">heteronormativen</a> Norm entspricht.\
          Queer wird auch verwendet, um Bewegungen\
          und Dinge zu bezeichnen, die mit queeren Menschen in Verbindung stehen, wie zum Beispiel die queere Szene, Queer Studies\
          oder queere Filmfestivals.</p>\
          <p>Der Begriff kommt aus dem Englischen und bezeichnet zunächst Dinge oder Personen, die meist im negativen Sinn von der\
          Norm abweichen. Er lässt sich mit „seltsam“, „eigenartig“ oder „sonderbar“ übersetzen. Er wurde benutzt, um abwertend\
          insbesondere über Homosexuelle aber auch andere Personen zu sprechen, deren geschlechtliche Identität und/oder\
          sexuelle Orientierung nicht der heteronormativen Norm entspricht. Im Zuge der Aids-Bewegung gelang es der queeren Community\
          jedoch, den Begriff wieder aufzuwerten (reclaiming), sodass für viele Menschen queer heute ein positiver Begriff ist und sie\
          sich gerne queer nennen. Als Sammelbegriff ist das Wort sehr offen und bietet vielen Menschen ein Identifikationsangebot.</p>\
          <a target="_blank" rel="noopener" href="https://diversity-arts-culture.berlin/woerterbuch/queer">https://diversity-arts-culture.berlin/woerterbuch/queer</a><br />\
          <a target="_blank" rel="noopener" href="https://de.wikipedia.org/wiki/Queer">https://de.wikipedia.org/wiki/Queer</a>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0,
          title: 'Wie viele Geschlechtsidentitäten gibt es?',
          text: `\
          <p>Gender ist ein Spektrum, es gibt daher keine Zahl. Grundsätzliche Versuche der Kategorisierung im modernen Westen gehen von \
          männlich, weiblich und ungeschlechtlich (agender) aus, sowie Mischformen (para=neben, demi=mittel, libra=ausgewogen), Menschen die\
          mehrere Geschlechter (bi, poly, pan), verschiedenen abwechselnd (fluid, flux), keinem völlig (gray) oder die Gender\
          als Konzept ablehnen (exgender). Darüber hinaus\
          gibt es in anderen und traditionellen Kulturen andere Bezeichnungen für nichtbinäre Menschen.
          Nicht alle Menschen, auf die diese Definitionen zutreffen, nutzen diese Bezeichnungen. Ein Versuch der Visualsierung:</p>\
          <div class="text-center"><img width="60%" src="static/Gender_pyramid_labeled.png"\
          /></div> Weiterführende Informationen: \
          <a target="_blank" rel="noopener" href="https://nibi.space/liste_nichtbin%C3%A4rer_identit%C3%A4ten">Liste nicht-binärer Identitäten</a>.\
          Bild: <a target="_blank" rel="noopener" href="https://lgbta.wikia.org/wiki/User_blog:Chaoticcylinder/View_on_Gender,_Non-Outherine,_and_Coining_a_New_Term">lgbta.wikia.org</a>\
          `,
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0,
          title: 'Ist Gender/Geschlechtsidentität/etc. eine Modeerscheinung?',
          text: `\
          <p>Es gibt viele traditionelle Kulturen, in denen es mehr als zwei Geschlechterkategorien gibt oder\
          gab (wie z.B. mit den Two Spirits bei den amerikanischen Ureinwohnern, die Mahu in Hawaii oder die\
          Muxe in Mexiko). Auch in der\
          europäischen Geschichte gibt es einige Hinweise jenseits der strengen Zweigeschlechtlichkeit.\
          In Platon’s Mythos der «Kugelmenschen»\
          (<a target="_blank" rel="noopener" href="https://de.wikipedia.org/wiki/Kugelmenschen">Wikipedia</a>)\
          gibt es auch etwas wie ein non-binäres Geschlecht.</p>\
          <p>Es zeichnet sich ab, dass jüngere Generationen die strenge Zweiteilung von Geschlecht nicht\
          mehr so selbstverständlich übernehmen. </p>\
          <a target="_blank" rel="noopener" href="https://www.nonbinary.ch/non-binaer-gibt-es-das-wirklich/">https://www.nonbinary.ch/non-binaer-gibt-es-das-wirklich/</a>\

          `,
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0,
          title: 'Wie spricht man nichtbinäre Menschen an?',
          text: `\
          <p>Grundsätzlich gibt es viele  genderneutrale Formen, z.B. statt "Sehr geehrte Damen und Herren",\
          "Guten Tag" oder wenn der Namen der Person bekannt ist "Guten Tag XY", "Liebe:r XY".</p>
          <p>Wo es keine genderneutrale Form gibt, können gendergerechte Formen benutzt werden.\
          Der Gender-Gap (Mitarbeiter_innen) bzw. das Binnen-I (StudentInnen)\
          ist dabei nicht mehr gebräuchlich, weil es als wenig inklusiv gilt und nur Männer und Frauen meint.\
          Gender Sternchen und Doppelpunkt werden als inklusiver empfunden (Mitarbeiter*innen, Student:innen).\
          Sternchen und Doppelpunkt spricht man als kurze Pause.\
          <a target="_blank" rel="noopener" href="https://www.derstandard.de/story/2000125170707/sternchen-gender-gap-oder-binnen-i-wie-gendert-mensch-richtig">\
          https://www.derstandard.de/</a></p>\
          <p>Darüber hinaus gibt es Initiativen, die sich mit genderneutraler Sprache beschäftigen, also\
          neuen genderneutralen Wortendungen statt, gegendertert Sprache:
          </p>
          <ul>
          <li><a target="_blank" rel="noopener" href="https://geschlechtsneutral.net/">https://geschlechtsneutral.net/</a><br /></li>
          <li><a target="_blank" rel="noopener" href="https://geschlechtsneutralesdeutsch.com/">https://geschlechtsneutralesdeutsch.com/</a></li>
          </ul>
          <p>Einige Menschen benutzen andere Pronomen als 'sie' und 'er'. Ähnlich wie man Menschen mit ihrem\
          Namen oder "hey du" ansprechen kann, ist auch das Benutzen der gewählten Pronomen der Person\
          ein Zeichen von Respekt und Höflichkeit. Wenn man sich nicht sicher ist, kann man danach Fragen\
          bzw. wenn man das nicht möchte, kann man seine Pronomen anbieten, indem an diese bei der Vorstellung\
          zusätzlich zu seinem Namen nennt. Auch cis Menschen können\
          ihre Pronomen anführen, um sich zu solidarisieren und das Thema zu normalisieren.
          Liste mit Neo-Pronomen: <a target="_blank" rel="noopener" href="https://nibi.space/pronomen">https://nibi.space/pronomen</a></p>\
          <p>Manche Menschen benutzen einen selbstgewählten Namen, der ihrer (Gender-)Identität besser entspricht\
          als jener, der ihnen bei ihrer Geburt gegeben wurde. Gerade für trans und nicht-binäre Menschen, die sich einen neuen Namen\
          gegeben haben, kann es extrem verletzend sein, sie mit ihrem Deadname anzusprechen. Das wird auch Deadnaming\
          oder deadnamen genannt und passiert manchmal unabsichtlich. Meist passiert es aber mit der Absicht, das\
          Geschlecht der trans oder nicht-binären Person nicht anzuerkennen, und sollte deshalb niemals getan werden.
          <a target="_blank" rel="noopener" href="https://queer-lexikon.net/2019/12/23/deadname/">\
          https://queer-lexikon.net/2019/12/23/deadname/</a></p>         
          <p>Manche Menschen sind nicht in allen Kontexten geoutet (z.B. nicht am Arbeitsplatz aus Angst vor Jobverlust)\
          daher ist es oft auch sinnvoll zu fragen, wo der gewählte Name und die Pronomen sicher benutzt werden\
          können.</p>\
          `,
        },
      ],
      faqklage: [
        {
          // eslint-disable-next-line no-multi-str
          title: 'Wer vertritt die Kläger*in?', text: '\
          <p>Dr. Helmut Graupner</p>\
          <a target="_blank" rel="noopener" href="https://www.graupner.at/">https://www.graupner.at/</a>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Wie lange dauert es bis zu einem Ergebnis?', text: '\
          <p>Realtisch sind 1-2 Jahre.</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Was hat es mit der Handlungsanleitung aus dem Innenministerium auf sich?', text: '\
          <p>Nach der Erkenntnis des VfGHs, dass die Geschlechtsidentität individuell ist und damit\
          der Person die geklagt hatte Recht zugeben ist, musste die Behörde handelnt. Zu diesem\
          Zweck wurde unter Kurz I unter Innenminister Kickl eine Weisung erlassen,\
          die dem Standesamt in Angelegenheiten zum\
          Personenstand insbesondere zum Geschlechtseintrag als Anleitung dient.</p>\
          <p>Diese wurde so eng wie möglich gefasst, d.h. sie erlaubt nur das minimal notwendige\
          um dem Urteil nicht zu widersprechen. Der Handlungsanleitung enthält in diesem Sinne\
          keine wesentlichen neuen Informationen, dass diese Anleitung nun aber öffentlich ist,\
          darf als Erfolg des Auskunftspflichtgesetzes gewertet werden. Außerdem haben wir damit\
          die Diskriminierung von trans und nicht-binäre Personen auch schwarz weiß.</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Muss man sich anschließen?', text: '\
          <p>Im Idealfall Nein. Das Gesetz  wurde das letzte Mal unter Kurz I und Innenminister Kickl\
          angepasst und damals wurde die Definition so eng gefasst, dass nur das minimal Notwendige\
          umgesetzt wurde, daher gibt es die alternativen Geschlechtseinträge aktuelle auch nur\
          für inter Personen. Darüber hinaus muss das Gesezt nach einem Urteil auch noch repariert werden, also ist davon\
          auszugehen, dass ähnlich wie bei der Öffnung der Ehe für gleichgeschlechtliche Paare die Umsetzung\
          dauert.</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Kann man sich anschließen?', text: '\
          <p>Gerne Kontakt aufnehmen!</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Ich möchte Helfen, was kann ich tun?', text: '\
          <p>Bewusstsein für trans und nicht-binäre Probleme im eigenen Umfeld erhöhen, \
          einer der oben verlinkten Organisationen beitreten und dort mitarbeiten, \
          die Kampagne teilen, Geld für die Klage spenden oder alles zusammen!</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Können bei Erfolg auch andere trans oder nicht-binäre Personen ihren Geschlechtseintrag ändern?', text: '\
          <p>Grundsätzlich ist das das Ziel. Welche Hürden ggf. bestehen bleiben und wogegen eventuell\
          nochmals geklagt werden muss, wird sich zeigen.</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Können bei Erfolg auch Cis Personen ihren Geschlechtseintrag ändern?', text: '\
          <p>Grundsätzlich sollte z.B. einer Streichung des Eintrags entsprechend dem Recht auf\
          individuelle Selbstbestimmung nichts im Wege stehen. Ob das dann Möglich sein wird oder\
          es ggf. einer weiteren Klage bedarf, wird sich zeigen.</p>\
          <p>Sollte dies Möglich sein, ist das aber kein Fehler oder Makel an der Nichtbinärität, sondern\
          zeigt lediglich die Absurdität des Geschlechtseintrags im Personenstandsregisters an und für sich auf.</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Was ist das Problem mit dem \'X\' im Reisepass?', text: '\
          <p>Das ‘X’ im Ausweis zwingt zu einem Outing und bietet damit sehr viel Angriffsfläche für Diskriminierung.\
          Besser wäre es, wenn man sich den Eintrag aussuchen könnte oder das Geschlecht gänzlich gestrichen wird.\
          In den Niederlanden wurde aus Schutz vor Diskriminierung bereits beschlossen, dass das Geschlecht nicht\
          mehr im Personalausweis stehen soll.</p>\
          <a target="_blank" rel="noopener" href="https://www.zeit.de/zett/queeres-leben/2021-04/geschlechtseintrag-divers-personalausweis-rafia-shahnaz-harzer/">https://www.zeit.de/zett/queeres-leben/2021-04/geschlechtseintrag-divers-personalausweis-rafia-shahnaz-harzer/</a><br />\
          <a target="_blank" rel="noopener" href="https://www.forbes.com/sites/jamiewareham/2020/07/07/dutch-id-cards-to-become-gender-free--could-more-of-europe-follow/">https://www.forbes.com/sites/jamiewareham/2020/07/07/dutch-id-cards-to-become-gender-free--could-more-of-europe-follow/</a>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          sec: 0, title: 'Müssen wir dann nochmal die Bundeshymne ändern?', text: '\
          <p>Grundsätzlich ist diese Überlegung nicht Teil der Kampagne. Dennoch klingt die Idee "Söhne und Töchter"\
          geschlechtsneutral z.B. zu "Kinder" umzuformulieren durchaus verlockend.</p>',
        },
      ],
      faqdonations: [
        {
          // eslint-disable-next-line no-multi-str
          title: 'Sind Spenden steuerlich absetzbar?', text: '\
          <p>Aktuell nicht, wir arbeiten an einer Lösung. Bitte gerne melden mit Ideen und Umsetzungs&shy;vorschlägen!</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Ich möchte in einer Crypto-Währung spenden, geht das?', text: '\
          <p>\
          Im Sinne der Umweltfreundlichkeit bitte bevorzugt per Überweisung spenden!<br /><br />\
          <small>BTC: 18LXMHVoA6dbJgr2fMGpKouJeavN273Db4<br />\
          ZRX: 0xb2d9db78Eb2B3Fa89f53ED0f60D5fc34e65a89d7<br />\
          AAVE: 0x32F079F16bA78d7F63c44e32105e74f1461d62dC<br />\
          ALGO: 5AQSGXXLHWLGX7NQ7R2BQRXZIZ7AWCTWF7QTV366JW3VWWXTUKCFSZ3TIY<br />\
          ANKR: 0x3CF0B470C5690393Bb667DDba4a60c0F370DfC12<br />\
          REP: 0xDADdA4083280dF96F4FA577a96b0CEE28935b486<br />\
          BAL: 0x2E7C81A65634c49aDAB685A9f751944E93f7f88B<br />\
          BNT: 0xc3Feb5F7754a2dA14215FDAdA4A9d7Cb641895B1<br />\
          BAND: 0x4996Af332df209f67dAF76DbF6200c711fD7E585<br />\
          BAT: 0xd63478B095A79C49415F0995Baa15d3D4398C60c<br />\
          BCH: qqqt3jny3psxjw3u7t4y2anr6nzqxn94uvcvklda9f<br />\
          ADA: addr1vyc9al0lt3ex3cc9r29jp7qsq9uezm90lgc3macyy0nc38cgh2kxk<br />\
          CGDL: 0x936e12c97429c037C2d208Afc4e6A4167BbbD0C9<br />\
          LINK: 0xCf532335399d5a395f50F6A81E9eaf7052b86678<br />\
          CVC: 0xff2E2D5f9D8d0A3dadbfed647Bf2CCB6bBDA3869<br />\
          COMP: 0x14017e4BdFdd66f457dDB9aE02C6E889E7176A55<br />\
          ATOM: cosmos187s4wm484xq7jyzlcc4d28r6u03j34f8v0vsmp<br />\
          CRV: 0x6aAFbCa5cF1f2a21024E10C0Af319565054CA5dD<br />\
          DAI: 0xE12219C6296b1f6bE62d9eb8f1751BA69466f009<br />\
          DASH: XgARhfj5DXtxk36KFHtekgKSAs9gVrFYov<br />\
          MANA: 0xd448D5a09eAc732A4f15B1F60eb4d6524fEd95A3<br />\
          ETH: 0x319120BDF6cBd3611Ff50d26A4f739aB5DB0987a<br />\
          ETC: 0x276062B87D1ec9052D4A8ECf3f9C2f5893e98797<br />\
          FIL: f1gypcbzu6oerxc2cwgn537zv5gingzfcarxah5iy<br />\
          KNC: 0x96db98A14F872042F89F891065310972dFbBdA75<br />\
          LTC: MQL9cd2DD3SeQjibZNbeQXe1PpGoGcxFUR<br />\
          LRC: 0x703e294b75daB2212e99882b04aB857a62Cb5237<br />\
          MKR: 0xAdEb84F321fb13845EE6ebc7dD5b0E6d19a4E875<br />\
          NU: 0xB551f95173a2255BAc97208a39d1e92563FC6fce<br />\
          NMR: 0x86819B2679104D612b8DC6C5Ee5A11Ce2a34359B<br />\
          OMG: 0xB26a0c643b6bEAE9143F76907f890aCc87382dD4<br />\
          OXT: 0x4C0860cab710A81c241775EA1Fa6F5165671E575<br />\
          MATIC: 0xC7815ED544c5AFb1F0DC0bfddE622000D89999F9<br />\
          REPV2: 0x2165bF20778F8DA680f701b11aed87366F8BCC4F<br />\
          REN: 0x913343BB4f0402aeFEf076c302BC94d83389fE5d<br />\
          SKL: 0x441B8b0d1c2479d562Cf615fA16Fd66d6056Ff4b<br />\
          STORJ: 0xcDDAd858fAcEaB9cD0a96ED56261Ca7fF78EB650<br />\
          SUSHI: 0xD25b42fAa6ddD73bF9ee338e65c1f1F1cb38cBDB<br />\
          SNX: 0x44162afaa248b235d3B8c242431B559b03E5A7D7<br />\
          GRT: 0xf7FBd0A8b2A123f92CfedC73aaC4E374Bd9F731D<br />\
          UMA: 0x1FeA254EDCB899A8b41AAf7604F2b4A9a0501473<br />\
          UNI: 0x6463DEEC0dbB5b1AAc5Db8C2A7cFb0dbc0253de3<br />\
          ZEC: t1URzKysdih7qYZsUZ3iK4vfzKjN6BtU13p<br />\
          DNT: 0x66628233f04718fAb21Dce248668c737177B3e2b<br />\
          JFY: 0x27567518b91547aA4b962eF415882BD316f3b468</small></p>\
          ',
        },
      ],
      faqwebsite: [
        {
          // eslint-disable-next-line no-multi-str
          title: 'Wie ist die Abgrenzung zwischen Venib und Genderklage?', text: '\
          <p>Genderklage ist eine Inniativate der Kläger*in, daher ist die Kläger*in redaktionell verantwortlich\
          für Genderkalge.at, Venib stellt die Infrastrkutur und kümmert sich um die Spendenabwicklung.\
          Aussendungen von Venib werden jedenfalls über die offiziellen Kanäle von Venib kommuniziert.</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Ich habe einen Fehler gefunden oder einen Vorschlag, an wen soll ich mich wenden?', text: '\
          <p>Bitte an die E-Mail Adresse im Impressum oder direkt einen Issue oder Pull-Request auf Github\
          erstellen (ebenfalls im Impressum verlinkt).</p>\
          ',
        },
        {
          // eslint-disable-next-line no-multi-str
          title: 'Wofür werden IP-Adressen verarbeitet und wie werden sie anonymisiert?', text: '\
          <p>Die IP-Adresse wird mit einer lokalen Datenbank verglichen, um den ungefähren Standort\
          zu ermitteln (z.B. Wien/Österreich). Die IP-Adresse wird dabei nicht an Dritte übertragen. Danach wird\
          sie gelöscht (gespeichert wird nur der ungefähre Standort).</p>\
          ',
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.main_content .accordion li {
  display: block;
}
</style>
<style scoped>

h3, .h3 {
  text-align: left;
  margin-top: 2rem;
}

</style>

<style>

.main_content .accordion p {
  text-align: left;
}

</style>
