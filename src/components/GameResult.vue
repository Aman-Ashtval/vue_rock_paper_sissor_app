<template>
    <div class="game-result-bg">
       <div>
         <span>YOU</span>
         <img :src="gameInfo.myChoice.imageUrl" alt="my choice" />
       </div>
       <div>
        <span>OPPONENT</span>
        <img :src="gameInfo.opponentChoice.imageUrl" alt="opponent choice" />
       </div>
       <div>
        <p>{{isWon ? "YOU WON" : "YOU LOSE"}}</p>
        <el-button plain @click="onRestartGame">Restart</el-button>
       </div>
    </div>
</template>

<script>

export default{
    name: 'GameRsult',
    data: function(){
        return{isWon: false}
    },
    props: {gameInfo: Object},
    methods:{
        onRestartGame: function(){
            this.$emit('reSetGame');
        }
    },
    mounted: function(){
        this.isWon = this.gameInfo.myChoice.id === this.gameInfo.opponentChoice.id;
    }
}
</script>

<style scoped>
.game-result-bg{
    width: 70%;
    margin: 32px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}

.game-result-bg div{
    width: 50%;
    padding: 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}

img{
    width: 180px;
    height: 180px;
    border-radius: 100%;
}

span{
    color: #ffffff;
    font-size: 22px;
    font-weight: 510;
    margin-bottom: 10px;
}

p{
    color: #ffffff;
    font-size: 28px;
    font-weight: 550;
    margin-bottom: 16px;
}

</style>