<script setup>
  import { computed, ref } from 'vue'
  const scorePlayer1 = ref(0)
  const scorePlayer2 = ref(0)


  const incrementScore = (player)=>{
    if (player === 1) {
      scorePlayer1.value += 1
    } else if (player === 2) {
      scorePlayer2.value += 1
    }
  }

  const restartGame = ()=>{
    scorePlayer1.value = 0
    scorePlayer2.value = 0
  }

  const isWinner = computed(()=>{
    if(scorePlayer1.value >= 5){
      return 'Player 1'
    } else if(scorePlayer2.value >= 5){
      return 'Player 2'
    }
    return 'No one yet'
  })

  
</script>

<template>
  <h1>The Best Simple Game</h1>
  <div class="scores">
    <h2 :class="scorePlayer1 >= 5 ? 'winner' : '' ">{{ scorePlayer1 }}</h2>
    <h2 :class="scorePlayer2 >= 5 ? 'winner' : '' ">{{ scorePlayer2 }}</h2>
  </div>
  <h3 v-if="scorePlayer1 >= 5 || scorePlayer2 >=5" >THE WINNER IS {{ isWinner }}</h3>
  <div class="buttons">
    <button @click="incrementScore(1)" :disabled="scorePlayer1 >= 5 || scorePlayer2 >=5">+1 Player 1</button>
    <button @click="incrementScore(2)" :disabled="scorePlayer1 >= 5 || scorePlayer2 >=5">+1 Player 2</button>
    <button @click="restartGame">Restart Game</button>
  </div>
</template>

<style scoped>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  h3{
    text-align: center;
    margin: 1em 0;
    color: #333;
  }
  .winner{
    color: green;
  }
  .scores{
    display: flex;
    gap: 1em;
    text-align: center;
    justify-content: center;
    padding: 1em;
  }
  .buttons{
    display: flex;
    flex-direction: column;
    gap: 1em;
    align-items: center;

    button{
      width: 100%;
      padding: 0.5em;
      border: 0;
      border-radius: 5px;
      cursor: pointer;
      background-color: #272727;
      color: #fff;
      font-size: 1em;
    }
    button:disabled{
      background-color: #ccc;
      cursor: not-allowed;
    }
  }
</style>