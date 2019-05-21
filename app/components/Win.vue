<template>
  <div class="win">
    
    <h1>{{ messageWin }}</h1>

    <router-link class="win-home" to="/">Go to Home</router-link>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');

.win{
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

.win h1{
  font-size: 50px;
  margin: 30px;
  text-align: center;
}

.win-home{
  color: black;
  font-size: 30px;
  text-decoration: none;
  margin-top: 40px;
  border: 2px solid black;
  padding: 30px;
  position: relative;
  overflow: hidden;
}

.win-home::after{
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

.win-home:hover::after{
  transform: translateX(0);
}


</style>

<script>
  export default {
    data() {
      return{
        messageWin: localStorage.getItem('endGameWin')
      }
    }
  }
</script>

