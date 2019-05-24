<template>
  <div class="lose">
     <audio  class="audioPlayer" autoplay preload="auto">
      <source src="musiqueLose.mp3" type="audio/mpeg">
      Your browser does not support the audio element.
    </audio>
    <button @click="PlaySong()" class="play"><img src="../assets/images/sound.png" alt=""></button>
    <button @click="PauseSong()" class="pause"><img src="../assets/images/mute.png" alt=""></button>

    <h1>
      {{ messageLose }}
    </h1>
    <img :src="gifLose">
    <transition name="pane">
      <router-link class="lose-home" to="/">Go to Home</router-link>
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


.lose{
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

.lose h1{
  font-size: 50px;
  margin: 30px;
  text-align: center;
}

.lose-home{
  color: black;
  font-size: 30px;
  text-decoration: none;
  margin-top: 40px;
  border: 2px solid black;
  padding: 30px;
  transition: background-color 0.5s, color 0.5s;
}

.lose-home:hover{
  background-color: black;
  color: white;
}


</style>

<script>

import game from '../data.json';



export default {
  data() {
    return{
      messageLose: localStorage.getItem('endGameLose'),
      gifLose: localStorage.getItem('gifLose')
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

