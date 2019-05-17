<template>
  <div class="persooo">
    <article v-on:click="selectPerso">
      <h2>{{ character.name }}</h2>
      <h3>{{ character.sexe }}</h3>
      <img :src="character.picture">
    </article>
  <div>
</template>

<script>
export default {
  props: ['character'],
  // methods: {
  //   selectPerso(){
  //     let persoSelect = document.querySelector('.persooo');
  //     persoSelect.addEventListener('click', () => {
  //       persoSelect.style.border = "2px solid black"
  //     })
  //   }
  // }
}
</script>