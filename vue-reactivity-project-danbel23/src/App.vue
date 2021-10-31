<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>{{ title }}</h1>
    <div class ="cart">
       <button class="cartButton" @click="addtoCart()">Add to Cart!</button>
       <button class="cartButton resetCart" @click="resetCart()">Reset Cart</button>
     </div>
     <div class ="cartAmount">
       <p>You have {{cartAmount}} points in the cart!</p>
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

export default {
  name: 'App',
  components: {
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
        King: require('./assets/ChessKing.jpeg')  
      },
      cartAmount: 0,
      clickedPiece: '',
      
    }
  },
  methods: {
    displayImage(piece) { 
      this.currentImage = this.chessImages[piece];
      this.clickedPiece = piece;    
    },
    addtoCart() {
      switch (this.clickedPiece) {
        case "Pawn":
          this.cartAmount++;
          break;
          case "Knight":
          this.cartAmount += 3;
          break;
          case "Bishop":
          this.cartAmount += 3;
          break;
          case "Rook":
          this.cartAmount += 5;
          break;
          case "Queen":
          this.cartAmount += 9;
          break;
          case "King":
          this.cartAmount += 22;
          break;
      }
    },
    resetCart() {
      this.cartAmount = 0;
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
  margin-bottom: 3.5rem;
}

.cartButton {
  padding: 1rem;
  margin-right: 3rem;
  display: flex;
  background-color: blue;
  color: gold;
  flex-direction: row;
  text-align: center;
  border-radius: 1.5rem;
}
.resetCart {
  background-color: purple;
}
.cartButton:hover {
  transform: scaleX(1.2) scaleY(1.2);
  border-radius: 0.5rem;
}
</style>
