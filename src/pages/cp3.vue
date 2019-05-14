<template>
  <div>
    <!-- Ligne Global Séparée en 2 -->
    <div class="row gutter-xs">
      <!-- Taille Cadre ( gauche ) -->
      <div class="col-6">
        <!-- Premier Cadre ( gauche ) -->
        <div class="cadreleft">
          <!-- En-tête cadre gauche -->
          <div class="header">
            <!-- Sur-titre -->
            <!-- <div class="surtitre">Animation conquête</div> -->
            <!-- Titre Principal -->
            <!-- <p class="titreprincipal">Puissance 3</p> -->
            <!-- Logo -->
            <div class="logo"><img src="assets/test3.png"></div>
          </div>
          <!-- Texte Objectifs -->
          <div class="texte">
            <center>
              <p>NOTRE AMBITION</p>
              <span class="souligner">2000 nouveaux clients</span> et <span class="souligner">2500 nouveaux sociétaires</span>
              <p>pour la durée du 05/11/2018 au 01/12/2018</p>
            </center>
          </div>
          <!-- Compteur général -->
          <center>
            <h4>Nombre de Conquêtes Val-De-France *</h4>
            <div>
              <div id="odometer" class="odometer">{{nombreconquetevdf}}</div>
            </div>
          </center>
          <!-- Compteur nouveaux sociétaires -->
          <center>
            <h4>Nombre de nouveaux sociétaires *</h4>
            <div class="compteurnewsocietaires">
              {{nombrenewsocietaires}}
            </div>
            <!-- Temps restant -->
            <p class="texte">Temps restant avant la fin de l'animation :</p>
            <div class="countdown">
              <div class="timer">
                <span id="days"></span> Jour(s)
                <span id="hours"></span> Heure(s)
                <span id="minutes"></span> Minute(s)
                <span id="seconds"></span>
              </div>
            </div>
          </center>
        </div>
      </div>
      <!-- Taille Cadre ( droit ) -->
      <div class="col-6 gutter-xs">
        <!-- Deuxième Cadre invisible ( droit ) -->
        <div class="cadreright">
          <!-- Cadre Conquêtes Par Marchés -->
          <div class="cadrerighttop">
            <!-- En-tête Cadre Conquêtes Par Marchés -->
            <div class="headercadrerighttop">
              <!-- Titre Cadre Conquêtes Par Marchés -->
              <p class="titrecpm">
                Conquêtes par Marchés *
              </p>
            </div>
            <!-- Liste Conquêtes Par Marchés -->
            <div class="info">
              <div class="barreinfo1">
                <q-icon name="mdi-account-group" />PART {{nombrepart}}
              </div>
              <div class="barreinfo3">
                <q-icon name="work_outline" />PRO {{nombrepro}}
              </div>
              <div class="barreinfo2">
                <q-icon name="mdi-link-variant" />ASSO {{nombreasso}}
              </div>
              <div class="barreinfo4">
                <q-icon name="mdi-tractor" />AGRI {{nombreagri}}
              </div>
            </div>
          </div>
        </div>
        <!-- Ligne séparée en 2 -->
        <div class="row gutter-xs">
          <!-- Cadre EERD Tablettes -->
          <div class="col-6">
            <div class="cadreEERD">
              <div class="headercadreEERD">
                <p class="titreEERD">
                  <q-icon name="tablet_android" /> EERD Tablettes *</p>
              </div>
              <div class="EERD">
                <p>{{nombreEERD}}</p>
              </div>
            </div>
          </div>
          <!-- Cadre Conquêtes mise en portefeuille -->
          <div class="col-6">
            <div class="cadreCMEP">
              <div class="headercadreCMEP">
                <p class="titreCMEP">
                  <q-icon name="account_balance_wallet" />Conquêtes mise en portefeuille **</p>
              </div>
              <div class="CMEP">
                <p>{{nombreCMEP}}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row asterix">
      <p class="asterix">(*) Compteur quotidien Source RAC Dernière mise à jour le {{datecq}} à {{heurecq}}, (**) Compteur hebdomadaire mis à jour le {{datech}} à {{heurech}}</p>
    </div>
  </div>
</template>

<style scoped>
  /* Titre principal */
  .titreprincipal {
    font-size: 350%;
    text-align: center;
    color: rgb(255, 255, 255);
  }
  /* Style cadre gauche général */
  .cadreleft {
    border-color: #808080;
    border-style: solid;
    border-width: 7px;
    border-radius: 40px;
    height: 97vh;
    background-color: #F2F2F2;
  }
  /* En-tête cadre gauche */
  .header {
    border-color: #808080;
    border-style: solid;
    border-width: 10px;
    background-color: #808080;
    border-radius: 30px 30px 0px 0px;
    height: 13vh;
    text-align: center;
  }
  /* Surtitre "Animation conquête" */
  .surtitre {
    text-align: center;
    color: rgb(255, 255, 255);
    font-size: 25px;
  }
  /* Titre Conquêtes mise en portefeuille */
  .titreCMEP {
    font-size: 80%;
    text-align: center;
    color: rgb(255, 255, 255);
    vertical-align: middle;
    margin: 2%;
  }
  /* Titre EERD tablettes */
  .titreEERD {
    font-size: 80%;
    text-align: center;
    color: rgb(255, 255, 255);
    vertical-align: middle;
    margin: 7%;
  }
  /* Titre Conquête Par Marchés */
  .titrecpm {
    font-size: 3em;
    text-align: center;
    color: rgb(255, 255, 255);
    vertical-align: middle;
    margin: 2%;
  }
  /* Logo de l'animation */
  .logo {
    font-size: 100px;
    color: rgb(255, 255, 255);
    position: absolute;
    width: 50%;
    height: 50%;
    top: 1%;
    left: 1%;
  }
  /* Texte général */
  .texte {
    font-size: 30px;
    margin: 50px;
  }
  /* Souligner */
  .souligner {
    text-decoration: underline;
  }
  /* Taille pour compteur général */
  .odometer {
    font-size: 100px;
  }
  /* Taille compteur nouveaux sociétaires */
  .compteurnewsocietaires {
    font-size: 100px;
  }
  /* Compte à rebours */
  .timer {
    display: center;
    flex-direction: line;
    margin: 50px;
    font-size: 30px;
    text-align: center;
  }
  /* Cadre en haut à droite " Conquêtes par marchés" */
  .cadrerighttop {
    border-color: #808080;
    border-style: solid;
    border-width: 7px;
    border-radius: 40px;
    height: 50vh;
    background-color: #F2F2F2;
  }
  /* En-tête Cadre en haut à droite " Conquêtes par marchés */
  .headercadrerighttop {
    border-color: #808080;
    border-style: solid;
    border-width: 10px;
    background-color: #808080;
    border-radius: 30px 30px 0px 0px;
    height: 13vh;
    text-align: center;
  }
  /* Tille police INFO ( PART PRO ASSO AGRI ) */
  .info {
    font-size: 40px;
  }
  /* PART */
  .barreinfo1 {
    text-align: center;
    margin-top: 7%;
    width: 50%;
    float: left;
  }
  /* ASSO */
  .barreinfo2 {
    text-align: center;
    margin-top: 14%;
    width: 50%;
    float: left;
  }
  /* PRO */
  .barreinfo3 {
    text-align: center;
    margin-top: 7%;
    width: 50%;
    float: right;
  }
  /* AGRI */
  .barreinfo4 {
    text-align: center;
    margin-top: 14%;
    width: 50%;
    float: right;
  }
  /* Cadre EERD Tablettes */
  .cadreEERD {
    border-color: #808080;
    border-style: solid;
    border-width: 7px;
    border-radius: 40px;
    height: 46vh;
    text-align: center;
    font-size: 50px;
    background-color: #F2F2F2;
  }
  /* Centrer le nombre EERD */
  .EERD {
    text-align: center;
    margin-top: 20%;
    width: 100%;
  }
  /* En-tête Cadre EERD */
  .headercadreEERD {
    border-color: #808080;
    border-style: solid;
    border-width: 10px;
    background-color: #808080;
    border-radius: 30px 30px 0px 0px;
    height: 13vh;
  }
  /* Cadre Conquêtes mise en portefeuille */
  .cadreCMEP {
    border-color: #808080;
    border-style: solid;
    border-width: 7px;
    border-radius: 40px;
    height: 46vh;
    text-align: center;
    font-size: 50px;
    background-color: #F2F2F2;
  }
  /* Center le nombre CMEP */
  .CMEP {
    text-align: center;
    margin-top: 20%;
    width: 100%;
  }
  /* En-tête Cadre Conquêtes mise en portefeuille  */
  .headercadreCMEP {
    border-color: #808080;
    border-style: solid;
    border-width: 10px;
    background-color: #808080;
    border-radius: 30px 30px 0px 0px;
    height: 13vh;
  }
  /* Texte pour astérix en bas de page */
  .asterix {
    text-align: center;
    width: 100%;
    margin-bottom: 0;
    font-size: 120%;
  }
  /* Cacher les secondes */
  #seconds {
    display: none;
  }
</style>

<script type="text/javascript">
export default {
  name: 'cp3',
  data () {
    return {
      opened: false,
      nombrepart: null,
      nombrepro: null,
      nombreasso: null,
      nombreagri: null,
      nombreconquetevdf: null,
      nombrenewsocietaires: null,
      nombreEERD: null,
      nombreCMEP: null,
      datecq: null,
      heurecq: null,
      datech: null,
      heurech: null
    }
  },
  mounted: function () {
    this.$axios.get('statics/result.json')
      .then((res) => {
        this.nombrepart = res.data.nombrepart
        this.nombrepro = res.data.nombrepro
        this.nombreasso = res.data.nombreasso
        this.nombreagri = res.data.nombreagri
        this.nombreconquetevdf = res.data.nombreconquetevdf
        this.nombrenewsocietaires = res.data.nombrenewsocietaires
        this.nombreEERD = res.data.nombreEERD
        this.nombreCMEP = res.data.nombreCMEP
        this.datecq = res.data.datecq
        this.heurecq = res.data.heurecq
        this.datech = res.data.datech
        this.heurech = res.data.heurech
      })
      .catch((error) => {
        console.log('coucou: ', error)
      })
  }
}
function countdown (endDate) {
  let days, hours, minutes, seconds
  endDate = new Date(endDate).getTime()
  if (isNaN(endDate)) {
    return
  }
  setInterval(calculate, 1000)
  function calculate () {
    let startDate = new Date()
    startDate = startDate.getTime()
    let timeRemaining = parseInt((endDate - startDate) / 1000)
    if (timeRemaining >= 0) {
      days = parseInt(timeRemaining / 86400)
      timeRemaining = (timeRemaining % 86400)
      hours = parseInt(timeRemaining / 3600)
      timeRemaining = (timeRemaining % 3600)
      minutes = parseInt(timeRemaining / 60)
      timeRemaining = (timeRemaining % 60)
      seconds = parseInt(timeRemaining)
      document.getElementById('days').innerHTML = parseInt(days, 10)
      document.getElementById('hours').innerHTML = ('0' + hours).slice(-2)
      document.getElementById('minutes').innerHTML = ('0' + minutes).slice(-2)
      document.getElementById('seconds').innerHTML = ('0' + seconds).slice(-2)
    } else {}
  }
}
// Paramétrage de la date final pour le compte à rebours
(function () {
  countdown('12/01/2018 00:00:00 AM')
}())
// var odometer = require('odometer')
</script>
