<template>
    <div class="header-bg">
        <div>
            <p>ROCK</p>
            <p>PAPER</p>
            <p>SCISSOR</p>
        </div>
        <div class="score-bg">
            <span>Score</span>
            <span class="score">{{score}}</span>
        </div>
    </div>
</template>

<script>
export default{
    name: 'GameHeader',
    props: {score: Number}
}
</script>

<style scoped>
.header-bg{
    width: 70%;
    padding: 16px;
    border: 2px solid #ffffff;
    border-radius: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

p{
    color: #ffffff;
    font-size: 22px;
    font-weight: normal;
    margin: 0px 0px 10px 0px;
    font-family: 'Bree Serif';
}

.score-bg{
    color: #223a5f;
    font-size: 16px;
    font-weight: bold;
    width: 100px;
    height: 100%;
    background-color: #ffffff;
    border-radius: 15px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.score{
    font-size: 32px;
}
</style>