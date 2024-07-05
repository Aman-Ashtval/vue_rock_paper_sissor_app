<template>
  <el-container class="app-bg" direction="vertical">
    <GameHeader :score="score" />
    <GamePlay v-if="!showResult" v-on:setTurn="yourTurn($event)" />
    <GameResult v-else :gameInfo="{myChoice, opponentChoice}" v-on:reSetGame="onRestart" />
    <GameRule />
  </el-container>
</template>

<script>
import GameRule from './components/GameRule.vue'
import GameHeader from './components/GameHeader.vue';
import GamePlay from './components/GamePlay.vue';
import GameResult from './components/GameResult.vue';

export default {
  name: 'App',
  components: {GameHeader, GameRule, GameResult, GamePlay},
  data: function(){
    return {score: 0, myChoice: null, opponentChoice: null, showResult: false}
  },
  methods:{
    yourTurn: function(gameData){
      this.myChoice = gameData.myChoice;
      this.opponentChoice = gameData.opponentChoice;
      this.showResult = true;
      this.score = gameData.myChoice.id === gameData.opponentChoice.id ? this.score + 1 : this.score - 1;
    },
    onRestart: function(){      
      this.myChoice = null;
      this.opponentChoice = null;
      this.showResult = false;
    }
  }
}
</script>

<style>
*{
  font-family: 'Roboto', 'Bree Serif', sans-serif;
  box-sizing: border-box;
}

.app-bg{
  width: 100%;
  height: 100vh;
  padding: 32px;
  background-color: #223a5f;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}
</style>
