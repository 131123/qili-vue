<template>
    <div class="tag-container">
        <span v-for="(item, index) in tags" :key="index" class="tag-item">{{ item }}</span>
    </div>
    <div class="share">
        <div class="left">
            <span>分享至</span>
            <svg-icon name="share" width="20px" height="20px"></svg-icon>
        </div>
        <div class="right">
            <span>投诉或建议</span>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const tags = ref(['化学', '高中生', '高中化学', '高考化学', '首页推荐', '高中物理', '高考物理', '高考化学', '首页推荐', '高中物理', '高考物理'])

</script>
<style scoped lang="scss">
.tag-container {
    align-items: center;
    display: flex;
    flex-wrap: wrap;
    grid-gap: 10px;
    gap: 10px;
    padding-bottom: 20px;
    margin: 0 56px;
    border-bottom: 1px solid #f1f2f3;

    .tag-item {
        align-items: center;
        background: #f1f2f3;
        border-radius: 35px;
        color: #61666d;
        display: block;
        display: flex;
        font-size: 15px;
        height: 29px;
        line-height: 29px;
        overflow: hidden;
        padding: 0 12px;
        -webkit-user-select: none;
        -moz-user-select: none;
        user-select: none;

        &:hover {
            color: #3783ed;
        }
    }
}

.share {
    align-items: center;
    box-shadow: inset 0 1px 0 var(--bg3);
    display: flex;
    justify-content: space-between;
    margin: 0 56px;
    padding: 20px 0 38px;

    .left {
        display: flex;
        align-items: center;
        cursor: pointer;

        &:hover {
            color: #3783ed;
        }

    }

    .right {
        cursor: pointer;

        &:hover {
            color: #3783ed;
        }

    }

}
</style>