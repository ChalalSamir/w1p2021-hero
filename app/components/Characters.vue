<template>
  <div class="big-header">
    <h1>Choisissez votre personnage</h1>

    <Character 
      v-for="character in characters"
      v-bind:character="character"
      v-bind:key="character.name"
    >

    </Character>

    <router-link class="button" to="/game/1">Go to Game</router-link>
  </div>
</template>

<script>
import Character from './Character.vue'
export default {
  data: function(){
    return{
      characters: [
        {
          name: 'Teddy Boirin',
          sexe: 'Homme',
          picture: 'http://www.sweethome3d.com/models/plant.png'
        },
        {
          name: 'Mélissa Gusatovic',
          sexe: 'Femme',
          picture: 'http://www.sweethome3d.com/models/plant.png'
        }
      ]
    }
  },
  components: {
    Character
  }
};
</script>

