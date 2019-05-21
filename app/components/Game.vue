<template>
  <div class="game">
    <h1>{{ step.title }}</h1>

    <ul>
      <li v-on:click="doActions(action)"
          v-for="action in step.actions"
          v-bind:action="action"
          v-bind:key="action.title"
          v-show="canDoAction(action)"
          class="choix"
          >
        <div>
          {{ action.title }}
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');

.game {
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  background-color: #c23616;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-family: 'Indie Flower';
}

.game h1 {
  text-align: center;
  font-size: 40px;
  margin: 40px 70px;
  line-height: 130%;
}

.game ul  {
  display: flex;
  width: 100vw;
  flex-direction: row;
  justify-content: center;
  margin-top: 20px;
  font-size: 35px;

}

.choix {
  padding: 20px;
  margin: 20px 40px;
  text-decoration: none;
  border: 2px solid black;
  width: 25%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.choix::after{
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

.choix:hover::after{
  transform: translateX(0);
}

.game ul li a {
  color: black;
  text-decoration: none;
}


</style>


<script>
  import game from '../data.json';

  export default {
    data: function() {
      return {
        step: this.getStep(),
        lose: 'true'
      }
    },
    mounted: function() {
    },
    watch: {
      '$route.params.id' (to, from) {
        this.step = this.getStep();
      }
    },
    methods: {
      getStep(){
        return this.step = game.steps.find( step => {
          return step.id === parseInt(this.$route.params.id)
        })
      },
      doActions(action){
        if(action.to) {
          this.$router.push({params: {id: action.to}})
        } 
        if(action.lose === true){
          localStorage.setItem('endGameLose', action.label)
          this.$router.push({path: '/lose'})
        }
        if(action.win === true){
          localStorage.setItem('endGameWin', action.label)
          this.$router.push({path: '/win'})
        }
      },
      canDoAction(action) {
        if (action.onlyMan && localStorage.getItem('sexe') !== 'homme') {
          return false;
        }
        if (action.onlyWoman && localStorage.getItem('sexe') !== 'femme') {
          return false;
        }

        return true;
      }
    }
  }
</script>

<style>



</style>

