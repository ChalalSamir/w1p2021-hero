<template>
<transition name="characters" appear >
  <div class="big-header">
    <h1>Choisissez votre personnage</h1>

    <div class="charac">

          <Character 
      v-for="character in characters"
      v-bind:character="character"
      v-bind:key="character.name"
    >

    </Character>

    </div>


    <router-link class="button" to="/game/1">Go to Game</router-link>
  </div>
</transition>
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
