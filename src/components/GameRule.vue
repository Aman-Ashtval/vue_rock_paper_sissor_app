<template>
    <el-button plain @click="centerDialogVisible = true" class="game-rule-btn">
        Ruls
    </el-button>

    <el-dialog v-model="centerDialogVisible" align-center  :show-close="false">

        <div class="dilog-body">
            <el-button type="primary" circle style="align-self: flex-end;" @click="centerDialogVisible=false">
                <el-icon style="vertical-align: middle">
                    <Close />
                </el-icon>
            </el-button>
            <img src="https://assets.ccbp.in/frontend/react-js/rock-paper-scissor/rules-image.png " alt="rules" class="game-rule-img" />
        </div>
    </el-dialog>
</template>

<script>
import {
    Close
} from '@element-plus/icons-vue';

export default {
    name: 'GameRule',
    components: {Close},
    data: function () {
        return {
            centerDialogVisible: false
        }
    }
}
</script>

<style scoped>
.dilog-body {
    max-height: 100vh;
    padding: 16px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
}

.game-rule-img {
    width: 80%;
    height: 80%;
    border-radius: 15px;
    margin-top: 16px;
}

.game-rule-btn{
    align-self: flex-end;
    color: #223a5f;
    font-size: 16px;
    font-weight: normal;
    padding: 7px 15px;
}
</style>
