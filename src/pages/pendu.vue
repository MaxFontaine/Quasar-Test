<template>
<div>
    <div class="Title">
      Jeu du Pendu :
    </div>
    <div class="Saisie">
      Saisir un mot secret :<br/>
      <input type="text" v-model="MotSaisie" id="entree" style="text-transform: lowercase">
    </div>
      <div class="button">
        <input type="button" value="Lancer" @click="add()">
      </div>
    <div class="Saisie">
      Entrez une lettre :
      <div class="button">
        <input type="text" v-model="lettre" id="entree" maxlength="1" style="text-transform: lowercase">
      </div>
    </div>
    <div class="Vérification">
        <input type="button" value="Vérifier" @click="verif()">
    </div>
    <div class="Récap">
          <p style="souligner" v-for="(lettre, index) in MotSecret" :key="index">
            [
          <span v-if="MotSecretBool[index]">
            {{lettre}}
          </span>
          ]
        </p>
        <ul>
      Nombre d'Erreur(s) : {{NbErreur}}<br />
      Nombre de Bonnes Lettres : {{NbBonneLettre}}<br />
      Lettres Fausses : {{LettreFausse}}<br />
      {{MotSaisie}}
        </ul>
      </div>
</div>
</template>

<script>
export default {
  name: 'pendu',
  data: () => {
    return {
      MotSecret: [],
      MotSecretBool: [],
      LettreDejaTape: [],
      LettreFausse: [],
      lettre: null,
      NbBonneLettre: 0,
      NbErreur: 0,
      LongueurMot: null,
      MotSaisie: null
    }
  },
  methods: {
    add: function () {
      let word = this.MotSaisie.toLowerCase()
      // Découpage Mot Secret
      this.MotSecret = Array.from(word)
      console.log(this.MotSecret)
      // Création Tableau avec autant de true/false que de lettres dans le mot secret
      for (let i = 0; i < this.MotSecret.length; i++) {
        this.MotSecretBool.push(false)
      }
      // console.log(this.MotSecretBool)
      this.LongueurMot = this.MotSecret.length
      // console.log(this.LongueurMot)
      this.MotSaisie = null
    },
    verif: function () {
      let i = this.MotSecret.indexOf(this.lettre)
      let j = this.LettreDejaTape.indexOf(this.lettre)
      if (j === -1) {
        if (i !== -1) {
          this.MotSecret.forEach((element, index) => {
            if (element === this.lettre) {
              this.LettreDejaTape.push(this.lettre)
              this.MotSecretBool[index] = !this.MotSecretBool[index]
              this.NbBonneLettre = this.NbBonneLettre + 1
            }
          })
        } else {
          this.NbErreur = this.NbErreur + 1
        }
      } else {
        alert('Lettre Déjà Tapé')
      }
      let k = this.LettreFausse.indexOf(this.lettre)
      if (k === -1) {
        if (i === -1) {
          this.LettreFausse.push(this.lettre)
        } else {
        }
      } else {
        alert('Lettre Déjà Tapé')
      }
      console.log(this.LettreFausse)
      console.log(this.LettreDejaTape)
      this.lettre = null
      this.NbErreur = this.LettreFausse.length
      if (this.NbBonneLettre === this.LongueurMot) {
        alert('Félicitations !!! Vous avez découvert le mot secret !')
      }
      if (this.NbErreur === 8) {
        alert('Vous avez Perdu !')
      }
    }
  }
}

</script>

<style>
.Title {
  text-align: center;
  font-size: 20px;
}
.Saisie {
  text-align: center;
  font-size: 20px;
}
.Vérification {
  text-align: center;
  font-size: 20px;
}
p {
  text-align: center;
  font-size: 20px;
}
ul {
  font-size: 20px;
  text-align: center;
}
.button {
  font-size: 20px;
  text-align: center;
}
div {
  padding: 1%;
}
</style>
