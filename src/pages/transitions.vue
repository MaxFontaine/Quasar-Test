<template>
    <div style="width: 500px; max-width: 90vw;">
      <p class="caption">"Slide" Transition</p>

      <p class="caption">
        Cliquez pour afficher l'image
      </p>
      <p>Off
        <q-toggle v-model="visible" label="On" />
      </p>

      <q-slide-transition>
        <p v-show="visible" style="margin: 0; max-width: 500px">
          <img class="responsive" src="~assets/quasar-logo-full.svg">
        </p>
      </q-slide-transition>
     <div style="width: 500px; max-width: 90vw;">
      <q-card style="margin-top: 25px">
        <q-card-title class="bg-primary text-center">
          <q-btn push color="orange" @click="show = !show">Toggle</q-btn>
        </q-card-title>
        <q-card-main>
          <div class="row q-px-sm q-pt-md gutter-sm">
            <q-select class="col-xs-12 col-sm-6" filter hide-underline v-model="enter" :options="enterSelectOptions" stack-label="CSS Enter Class"/>
            <q-select class="col-xs-12 col-sm-6" filter hide-underline v-model="leave" :options="leaveSelectOptions" stack-label="CSS Leave Class"/>
          </div>
        </q-card-main>
      </q-card>

      <q-card style="margin-top: 25px" class="overflow-hidden">
        <q-card-title class="text-center">
          Single
        </q-card-title>
        <q-card-main>
          <transition appear :enter-active-class="enterClass" :leave-active-class="leaveClass">
            <div v-if="show" v-html="loremipsum" />
          </transition>
        </q-card-main>
      </q-card>

      <q-card style="margin-top: 25px" class="overflow-hidden">
        <q-card-title class="text-center">
          Group
        </q-card-title>
        <q-card-main>
          <transition-group appear :enter-active-class="enterClass" :leave-active-class="leaveClass" class="group">
            <div v-if="show" v-for="n in 1" :key="n" v-html="loremipsum"/>
          </transition-group>
        </q-card-main>
      </q-card>
    </div>
  </div>
</template>

<script>
import {
  QSlideTransition,
  QToggle
} from 'quasar'
import {
  generalAnimations,
  inAnimations,
  outAnimations
} from 'quasar-extras/animate/animate-list.js'

function alphabetically (a, b) {
  return a.localeCompare(b)
}
function generateOptions (name) {
  return {
    label: name,
    value: name
  }
}
const enter = generalAnimations.concat(inAnimations).sort(alphabetically)
const leave = generalAnimations.concat(outAnimations).sort(alphabetically)

export default {
  components: {
    QSlideTransition,
    QToggle
  },
  data: () => {
    return {
      visible: true,
      enterSelectOptions: enter.map(generateOptions),
      leaveSelectOptions: leave.map(generateOptions),
      enter: 'bounceInLeft',
      leave: 'bounceOutRight',
      show: true,
      disable: false,
      loremipsum: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
    }
  },
  computed: {
    enterClass () {
      return `animated ${this.enter}`
    },
    leaveClass () {
      return `animated ${this.leave}`
    }
  }
}
</script>
