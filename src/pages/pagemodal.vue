<template>
  <body style="background-color:#888888;">
    <!-- Bouton accueil -->
    <q-btn @click="$router.push('/#')" color="primary" label="Accueil" />
    <!-- Bouton modal -->
    <q-btn color="primary" @click="opened = true" label="Ouvrir Modal">
    </q-btn>
    <!-- Forme de la modal -->
    <q-modal v-model="opened" :content-css="{minWidth: '80vw', minHeight: '80vh'}">
      <!-- Texte intérieur modal -->
      <center>
        <h4>Fiche Résultats :<br/>
          <br/>Compte tenu des informations saisies, le client entre dans la segmentation :</h4>
        <h3>INTERMÉDIAIRE</h3>
        <h4>Cette segmentation doit être associée à un portefeuille type :</h4>
        <h3>CONSEILLER PARTICULIERS</h3>
        <p>Pour plus d'informations concernant le résultat du simulateur vous pouvez consulter la documentation disponible sur le bouton ( informations ) en haut à droite de votre écran.</p>
      </center>
      <!-- Bouton close modal -->
        <center>
        <q-btn color="primary" @click="opened = false" label="Close" />
        </center>
    </q-modal>
    <div class="logo"><center><img src="assets/test3.png"></center></div>
     <div class="logo"><center><img src="assets/test.png"></center></div>
      <div class="logo"><center><img src="assets/vraitest.png"></center></div>
  </body>
</template>

<style>
</style>

<script>
export default {
  name: 'pagemodal',
  data () {
    return {
      opened: false
    }
  }
}
</script>
