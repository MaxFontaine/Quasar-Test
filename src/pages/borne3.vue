<template>
<body>
<div class="ImageDeFond">
  <img src="assets/ImageFondCA.jpg" width="1920px" height="1080" alt="">
</div>
<div class="Titre">Veuillez saisir votre Nom et votre Prénom :</div>
<form>
  <input type="text" value="" name="" style="margin-left:5%;width:40%;display:inline-block;">
</form>
<form>
<input type="text" value="" name="" style="margin-left:55%;width:40%;display:inline-block;">
</form>
<button class="boutonaccueil"><router-link to="/borne">Accueil</router-link></button>
</body>
</template>

<style>
.ImageDeFond {
  filter: blur(3px);
  z-index: -1;
}
.bouton1 {
  font-size: 35px;
  font-weight:bold;
  border-radius: 10px;
  border-style: solid;
  border-width: 1px;
  border-color: #fff;
  background-color: #00664b;
  background: rgba(0,0,0,.8);
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
  color: #fff;
  position: absolute;
  top: 40%;
  bottom: 40%;
  width: 20%;
  left: 20%;
  right: 40%;
}
.bouton2 {
  font-size: 35px;
  font-weight:bold;
  border-radius: 10px;
  border-style: solid;
  border-width: 1px;
  border-color: #fff;
  background-color: #00664b;
  /* background: rgba(0,0,0,.8); */
  background: rgba(0,102,75,.7);
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
  color: #fff;
  position: absolute;
  top: 40%;
  bottom: 40%;
  width: 20%;
  right: 20%;
}
.boutonaccueil {
  font-size: 25px;
  font-weight:bold;
  border-radius: 10px;
  border-style: solid;
  border-width: 1px;
  border-color: #fff;
  background-color: #00664b;
  background: rgba(0,0,0,.8);
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
  color: #fff;
  position: absolute;
  top: 2%;
  height: 8%;
  width: 10%;
  right: 2%;
}
.Titre {
  font-size: 45px;
  font-weight:bold;
  border-radius: 10px;
  border-style: solid;
  border-width: 1px;
  border-color: #fff;
  background: rgba(0,0,0,.7);
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
  color: #fff;
  position: absolute;
  top: 20%;
  height: 8%;
  width: auto;
  right: 20%;
  left: 20%;
  text-align: center;
}
a {
  text-decoration: none; color: white;
}
input {
  position: absolute;
  background: rgba(0,0,0,.7);
  /* background: rgba(0,102,75,.7); */
  backdrop-filter: grayscale(1) contrast(3) blur(1px);
  border-color: white;
  color:#fff;
  font-size: 45px;
  border-radius: 10px;
  top: 35%;
  height: 8%;
}

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
