<template>
    <div class="game-bg">
       <div v-for="choice in choicesList" :key="choice.id" class="choice-bg">
            <button type="button" @click="onClickButton(choice)">
                <img :src="choice.imageUrl" alt="choice" />
            </button>
       </div> 
    </div>
</template>

<script>
const choicesList = [
  {
    id: 'ROCK',
    imageUrl:
      'https://assets.ccbp.in/frontend/react-js/rock-paper-scissor/rock-image.png',
  },
  {
    id: 'SCISSORS',
    imageUrl:
      'https://assets.ccbp.in/frontend/react-js/rock-paper-scissor/scissor-image.png',
  },
  {
    id: 'PAPER',
    imageUrl:
      'https://assets.ccbp.in/frontend/react-js/rock-paper-scissor/paper-image.png',
  },
]


export default{
    name: 'GamePlay',
    data: function(){
        return {choicesList: [...choicesList]}
    },
    methods: {
        onClickButton: function(myChoice){
            const opponentChoice = this.choicesList[Math.floor(Math.random()*this.choicesList.length)];
            this.$emit('setTurn', {myChoice, opponentChoice});
        }
    }
}
</script>

<style scoped>
.game-bg{
    width: 70%;
    margin: 32px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}

.choice-bg{
    width: 50%;
    padding: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}

.choice-bg button{
    width: 160px;
    height: 160px;
    padding: 0px;
    background-color: transparent;
    border: none;
    border-radius: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

img{
    width: 100%;
    border-radius: 100%;
}
</style>