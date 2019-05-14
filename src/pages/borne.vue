<template>
<body>
<div class="ImageDeFond">
  <img src="assets/ImageFondCA.jpg" width="1920px" height="1080" alt="">
</div>
<div class="DivTitre">
    <span class="Titre">Bienvenue au Crédit Agricole Val de France</span>
  </div>
<button class="bouton"><router-link to="/borne2">Commencer ici</router-link></button>
</body>
</template>

<style>
.ImageDeFond {
  filter: blur(3px);
  z-index: -1;
}
.DivTitre {
  border-color: #fff;
  border-style: solid;
  border-width: 1px;
  position: absolute;
  width: auto;
  height: 300px;
  top: 20%;
  left: 30%;
  right: 30%;
  border-radius: 10px;
  background: rgba(0,0,0,.7);
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
}
.Titre {
  font-size: 68px;
  font-weight:bold;
  text-align: center;
  color: #fff;
  position: absolute;
  top: 10%;
  left: 5%;
  right: 5%;
  bottom: 10%;
  width: auto;
}
.bouton {
  font-size: 35px;
  font-weight:bold;
  border-radius: 10px;
  border-style: solid;
  border-width: 1px;
  border-color: #fff;
  background-color: #00664b;
  background: rgba(0,0,0,.7);
  background: rgba(0,102,75,.7);
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
  color: #fff;
  position: absolute;
  top: 65%;
  bottom: 20%;
  width: 20%;
  left: 40%;
  right: 40%;
}
a { text-decoration: none; color: white;}

</style>

<script>
export default {
  name: 'borne',
  data () {
    return {
    }
  }
}
</script>
