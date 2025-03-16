<template>
    <div class="layout">
        <div class="header">
            <p>推荐文章</p>
            <div style="search">
                <el-input v-model="searchColumn" placeholder="搜索专栏文章" suffix-icon="Search"></el-input>
            </div>
        </div>
        <div class="content">
            <contentItem ref="ColumnItem" v-for="i in 10" :key="i"></contentItem>
        </div>
    </div>

</template>

<script setup>
import contentItem from './contentItem'
import { ref, onMounted } from 'vue'


const ColumnItem = ref()

</script>
<style scoped lang="scss">
.layout {
    width: 680px;
    margin: auto;
    padding-top: 30px;

    .header {
        display: flex;
        justify-content: space-between;
        height: 40px;


        p {
            width: 72px;
            font-size: 18px;
            line-height: 40px;
        }

        .search {
            width: 260px;
        }
    }
}
</style>