<template>
  <q-page class="flex flex-center">
    <q-stepper ref="stepper">
      <!-- Step:1 -->
      <q-step default title="Situation Familiale">
        <p><center>Sélectionnez la situation Familiale * :</center></p>
        <q-select v-model="Options1" :options="selectOptions1"/>
      </q-step>
         <!-- Step:2 -->
      <q-step title="Catégorie PCS"><p><center>Sélectionnez la catégorie PCS * :</center></p>
        <q-select v-model="Options2" :options="selectOptions2"/></q-step>
      <!-- Step:3 -->
      <q-step title="Tranche D'âge"><p><center>Précisez la Tranche D'âge * :</center></p>
      <q-select v-model="Options3" :options="selectOptions3"/>
      <!-- Checkbox -->
      <br/><center><q-checkbox v-model="checked" label="Précisez si le client est retraité"></q-checkbox></center>
      <h1 v-if="checked">Yes</h1>
      <h1 v-else>No</h1>
      </q-step>
      <!-- Step:4 -->
      <q-step title="Montant de l'épargne et de flux annuel">
        <q-input v-model="text" float-label="Saisir le montant de l'épargne ( En K€ ) * :" />
        <q-input v-model="text" float-label="Saisir le montant de flux annuel ( En K€ ) * :" />
        <q-btn @click="$refs.stepper.next()" label="Simuler"/></q-step>
      <!-- Boutons navigation (next/previous) -->
      <q-stepper-navigation>
        <q-btn flat @click="$refs.stepper.previous()" label="Retour" />
        <q-btn @click="$refs.stepper.next()" label="Continuer" />
      </q-stepper-navigation>
    </q-stepper>
  </q-page>
</template>

<style>

.q-stepper-header {
  overflow: hidden;
  color: #008b92;
}
.q-stepper-tab.step-waiting .q-stepper-dot {
  color: #2E2E2E;
}
.q-btn {
  color: #008b92;
}
</style>

<script>
export default {
  name: 'Pagevif',
  data: () => {
    return {
      message: null,
      checked: false,
      Options1: null,
      Options2: null,
      Options3: null,
      selectOptions1: [
        {
          label: '1 Personne ( Célibataire, Veuf, Divorcé, Séparé)',
          value: 'solo'
        },
        {
          label: '2 Personnes ( Marié, Concubin )',
          value: 'duo'
        }
      ],
      selectOptions2: [
        {
          label: 'Agriculteur Grande exploitation',
          value: 'agri'
        },
        {
          label: "Chef d'entreprise 10 salariés ou plus",
          value: 'chef'
        },
        {
          label: 'Profession libérale',
          value: 'pl'
        },
        {
          label: 'Cadre fonction publique',
          value: 'cfp'
        },
        {
          label: 'Cadre administratif / commercial',
          value: 'cac'
        },
        {
          label: 'Ingénieur cadre techn.ent',
          value: 'ing'
        },
        {
          label: 'Ancien Cadre',
          value: 'anciencadre'
        },
        {
          label: 'Ancien artisan/commer/entrep',
          value: 'ancienartisant'
        },
        {
          label: 'Élèves - Étudiants',
          value: 'EE'
        },
        {
          label: 'Autres',
          value: 'autres'
        }
      ],
      selectOptions3: [
        {
          label: 'Moins de 30 ans',
          value: 'm30'
        },
        {
          label: '30 ans et plus ',
          value: 'p30'
        }
      ]

    }
  },
  mounted: function () {
    console.log(this.selectOptions1[0].label)
  }
}
</script>
