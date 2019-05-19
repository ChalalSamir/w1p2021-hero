<template>
<transition name="begin" appear >
    <div class="game">
    <h1>{{ step.title }}</h1>

    <ul>
      <li v-for="action in step.actions"
          v-bind:action="action"
          v-bind:key="action.title"
          >
        <router-link :to="action.to.toString()">
          {{ action.title }}
        </router-link>
      </li>
    </ul>
  </div>
</transition>
</template>

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
      }
    }
  }
</script>

<style>



</style>

