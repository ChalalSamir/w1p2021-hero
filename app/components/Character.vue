<template>
  <transition class="character" name="pane" v-on:click="persoo()">
    <article >
      <div >
        <h2>{{ character.name }}</h2>
        <h3>{{ character.sexe }}</h3>
        <img :src="character.picture">
      </div>
    </article>
  </transition>
</template>

<style scoped>

.character{
  display: flex;
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