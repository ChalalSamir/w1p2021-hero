<template>
  <div class="big-header">
    <h1>{{ message }}</h1>
    <br />
    <router-link class="button" to="/characters">Go to Characters</router-link>
  </div>
</template>

<script>
import countService from '../services/countService';

export default {
  data() {
    return {
      message: 'Bienvenue dans Happy BirthDEAD'
    };
  }
};
</script>
