<template>
  <div class="home">
    <h1>Bienvenue dans Happy BirthDEAD</h1>
    <br />
    <router-link class="home-perso" to="/characters">Choisir son personnage</router-link>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');

.home{
  height: 100vh;
  width: 100vw;
  background-color: #c23616;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  flex-direction: column;
  font-family: "Indie Flower"
}

.home h1{
  font-size: 50px;
}

.home-perso{
  color: black;
  font-size: 30px;
  text-decoration: none;
  margin-top: 40px;
  border: 2px solid black;
  padding: 30px;
  position: relative;
  overflow: hidden;
}

.home-perso::after{
  content: "Suivant";
  text-align: center;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: black;
  transform: translateX(-100%);
  transition: transform 0.7s;
  color: white;
}

.home-perso:hover::after{
  transform: translateX(0);
}


</style>


<script>
import countService from '../services/countService';

export default {
};
</script>
