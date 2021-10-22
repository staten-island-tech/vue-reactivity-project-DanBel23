<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>{{ title }}</h1>
    <div class="chessbuttons">
      <button>{{ chess1 }}</button>
      <button>{{ chess2 }}</button>
      <button>{{ chess3 }}</button>
      <button>{{ chess4 }}</button>
      <button>{{ chess5 }}</button>
      <button>{{ chess6 }}</button>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      title: 'Chess!',
      chess1: 'pawn',
      chess2: 'knight',
      chess3: 'bishop',
      chess4: 'rook',
      chess5: 'queen',
      chess6: 'king',
    }
  }
}


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.chessbuttons {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin:3 auto;
  
}
</style>
