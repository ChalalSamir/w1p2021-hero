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
  position: relative;
  overflow: hidden;
}

.characters-game::after{
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

.characters-game:hover::after{
  transform: translateX(0);
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
      if(character.name === "Teddy"){
        localStorage.setItem('sexe', 'homme')
      }
      if(character.name === "Melissa"){
        localStorage.setItem('sexe', 'femme')
      }
    }
  }
};
</script>

