<template>
  <div class="characters">
    <h1>Choisissez votre personnage</h1>

    <Character 
    v-for="character in characters"
    v-bind:character="character"
    v-bind:key="character.name"
    v-on:click="handleClick"
    >

    </Character>
    <router-link class="characters-game" to="/game/1">Jouer à Happy BirthDEAD</router-link>
  </div>
</template>

<style>

@import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');

.characters{
  padding: 30px;
  width: 100vw;
  min-height: 100vh;
  background-color: #c23616;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  flex-direction: column;
  font-family: "Indie Flower"
}

.characters h1{
  font-size: 50px;
}

.characters-game{
  color: black;
  font-size: 30px;
  text-decoration: none;
  margin-top: 40px;
  border: 2px solid black;
  padding: 30px;
  transition: background-color 0.5s, color 0.5s;
}

.characters-game:hover{
  background-color: black;
  color: white;
}

</style>


<script>
import Character from './Character.vue'
export default {
  data: function(){
    return{
      characters: [
        {
          name: 'Bart',
          sexe: 'Garçon',
          picture: 'http://www.stickpng.com/assets/thumbs/5a0c40785a997e1c2cea1168.png'
        },
        {
          name: 'Lisa',
          sexe: 'Fille',
          picture: 'https://upload.wikimedia.org/wikipedia/en/thumb/e/ec/Lisa_Simpson.png/220px-Lisa_Simpson.png'
        }
      ]
    }
  },
  components: {
    Character
  },
  methods: {
    handleClick(character) {
      if(character.name === "Bart"){
        alert('Vous avez choisi Bart')
        localStorage.setItem('sexe', 'garçon')
      }
      if(character.name === "Lisa"){
        localStorage.setItem('sexe', 'fille')
        alert('Vous avez choisi Lisa')
      }
    }
  }
};
</script>


<style>

@keyframes slidein {

  from {
    opacity: 0;
  }

  to {
    opacity: .9;
  }

}

.characters-enter-active {
  animation: slidein 3s;
}

.charac {
  display: flex;
  flex-direction: row;
  align-content: space-between;
  margin-top: 30px;
  margin-bottom: 30px;
}

</style>
