<template>
  <div class="win">
    <audio autoplay loop preload="auto">
      <source src="musiqueWin.mp3" type="audio/mpeg">
      Your browser does not support the audio element.
    </audio>
    <h1>{{ messageWin }}</h1>
    <img :src="gifWin">
    
    <transition name="pane">
      <router-link class="win-home" to="/">Go to Home</router-link>
    </transition>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');

.win{
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

.win h1{
  font-size: 50px;
  margin: 30px;
  text-align: center;
}

.win-home{
  color: black;
  font-size: 30px;
  text-decoration: none;
  margin-top: 40px;
  border: 2px solid black;
  padding: 30px;
  transition: background-color 0.5s, color 0.5s;
}

.win-home:hover{
  background-color: black;
  color: white;
}


</style>

<script>
  export default {
    data() {
      return{
        messageWin: localStorage.getItem('endGameWin'),
        gifWin: localStorage.getItem('gifWin')
      }
    }
  }
</script>

