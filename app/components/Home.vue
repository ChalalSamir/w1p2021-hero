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
  transition: background-color 0.5s, color 0.5s;
}

.home-perso:hover{
  background-color: black;
  color: white;
}


</style>


<script>
import countService from '../services/countService';

export default {
};
</script>

<style>

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: .9;
  }
}

.begin-enter-active {
  animation: fadeIn 2s;
  
  
}
</style>
