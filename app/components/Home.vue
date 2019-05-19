<template>
<transition name="begin" appear >
  <div class="big-header">
    <h1>{{ message }}</h1>
    <br />
    <transition name="play" appear :duration="100000" >
    <router-link class="button" to="/characters">Go to Characters</router-link>
    </transition>
  </div>
</transition>
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

<style>

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: .9;
  }
}

.begin-enter-active {
  animation: fadeIn 2s;
  
  
}
</style>
