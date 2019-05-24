<template>
  <transition name="pane">
    <article v-on:click="persoo()">
      <div>
        <h2>{{ character.name }}</h2>
        <h3>{{ character.sexe }}</h3>
        <img :src="character.picture">
      </div>
    </article>
  </transition>
</template>

<style scoped>

article{
  border: 2px solid black;
  padding: 20px;
  display: inline;
  margin: 30px;
}

h2, h3{
  font-size: 20px;
  text-align: center;
}

img{
  height: 200px;
}

</style>


<script>
export default {
  props: ['character'],
  methods: {
    persoo(){
      this.$emit('click', this.character);
    }
  }
}
</script>