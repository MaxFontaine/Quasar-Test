<template>
  <q-page class="center">
      <input v-model="message" placeholder="modifiez-moi" />
      <p>Le message est : {{ message }}</p>
 <span>Le message multiligne est :</span>
<p style="white-space: pre-line;">{{ message }}</p>
<br>
<textarea v-model="message" placeholder="ajoutez plusieurs lignes"></textarea>
</q-page>
</template>

<style>
</style>

<script>
export default {
  name: 'Pagevmodel',
  data: () => {
    return {
      message: null
    }
  }
}
</script>
