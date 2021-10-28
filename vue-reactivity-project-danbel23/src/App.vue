<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>{{ title }}</h1>
    <div class ="cart">
       <button class="cartButton" v-on:click="cart">Add to Cart!</button>
     </div>
    <div class="chessbuttons" >
      <button class ="btn"  v-for = "chessPiece in chessPieces" :key="chessPiece" @click="displayImage(chessPiece)" >{{chessPiece}}</button>
     </div>
     <div >
       <img class="chessP" v-bind:src= "currentImage">
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
      chessPieces: ['Pawn', 'Knight', 'Bishop','Rook','Queen','King'],
      currentImage:'',
      chessImages: {
        Pawn: require('./assets/Chesspawn.jpeg'), 
        Knight: require('./assets/Chessknight.jpeg'),
        Bishop: require('./assets/ChessBishop.jpeg'),
        Rook: require('./assets/ChessRook.jpeg'), 
        Queen: require('./assets/ChessQueen.jpeg'), 
        // King: require('./assests/ChessKing.jpeg')  
      },
      cart: [],
      
    }
  },
  methods: {
    displayImage(piece) { 
      this.currentImage = this.chessImages[piece];
          
    },
    addtoCart() {
      const cart = document.querySelector("cart");
      this.cart += 1;
      console.log(cart);
    }
  },
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
  flex-direction: row;
  margin:3 auto;
}
.chessP {
  height: 30rem;
  margin-top: 4rem;
}
.btn {
  padding: 1rem;
  display: flex;
  background-color: red;
  color: gold;
  flex-direction: row;
  text-align: center;
  border-radius: 1.5rem;
}
.btn:hover {
  transform: scaleX(1.2) scaleY(1.2);
  border-radius: 0.5rem;
}
.cart {
  display: flex;
  justify-content: center;
}
.cartButton {
  padding: 1rem;
  display: flex;
  background-color: blue;
  color: gold;
  flex-direction: row;
  text-align: center;
  border-radius: 1.5rem;
}
.cart:hover {
  transform: scaleX(1.2) scaleY(1.2);
  border-radius: 0.5rem;
}
</style>
