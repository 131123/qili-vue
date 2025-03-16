<template>
    <div class="main">
        <el-tabs v-model="activeName" class="demo-tabs" @tab-click="handleClick">
            <el-tab-pane label="评论 1080" name="first">
                <chat />
            </el-tab-pane>
            <el-tab-pane label="赞与转发 999" name="second">
                <like />
            </el-tab-pane>
        </el-tabs>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import like from '../compoent/like.vue'
import chat from '../compoent/chat.vue'

const activeName = ref('first')
const handleClick = (tab, event) => {
    console.log(tab, event)
}

</script>
<style scoped lang="scss">
.main {
    margin: 0 56px;
}
</style>