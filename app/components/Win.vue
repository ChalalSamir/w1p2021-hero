<template>
  <div class="win">
    <audio class="audioPlayer" autoplay preload="auto">
      <source src="musiqueWin.mp3" type="audio/mpeg">
      Your browser does not support the audio element.
    </audio>
    <button @click="PlaySong()" class="play"><img src="../assets/images/sound.png" alt=""></button>
    <button @click="PauseSong()" class="pause"><img src="../assets/images/mute.png" alt=""></button>
    <h1>{{ messageWin }}</h1>
    <img :src="gifWin">
    
    <transition name="pane">
      <router-link class="win-home" to="/">Go to Home</router-link>
    </transition>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');

.pause {
  border: none;
  background: none;

}

.pause img {
  height: 35px;
  width: 35px;

}

.play {
  border: none;
  background: none;

}

.play img {
  height: 35px;
  width: 35px;

}

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
    },
    methods: {
    PlaySong(){
  
      var song = document.querySelector('.audioPlayer');
      song.play();
    },
    PauseSong() {
      var song = document.querySelector('.audioPlayer');
       song.pause();
    }
  }
  }
</script>

