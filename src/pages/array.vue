<template>
  <div>
  <q-btn @click="add('A')">Ajouter A</q-btn>
  <q-btn @click="add('B')">Ajouter B</q-btn>
  <q-btn @click="add('C')">Ajouter C</q-btn>
  <q-btn @click="add('D')">Ajouter D</q-btn>
  </div>
</template>

<style>
</style>

<script>
export default {
  name: 'array',
  data: () => {
    return {
      fruits: []
    }
  },
  methods: {
    add: function (item) {
      if (this.fruits.indexOf(item) > -1) {
        let i = this.fruits.indexOf(item)
        this.fruits.splice(i, 1)
      } else {
        this.fruits.push(item)
      }
      console.log(this.fruits)
    }
  }
}
</script>
