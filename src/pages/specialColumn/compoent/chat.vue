<template>

    <div class="search">
        <div class="img">
            <img src="@/assets/img/user.webp" alt="">
        </div>
        <div class="search-input">
            <el-input v-model="searchKeyword" placeholder="尊重是评论打动人心的入场券"></el-input>
            <div class="but" v-show="searchKeyword">
                <el-button type="primary">发布</el-button>

            </div>
        </div>
    </div>
    <div class="main">
        <div v-for="item in 10" :key="item" class="item">
            <div class="top">
                <div class="user_img">
                    <img src="@/assets/img/user.webp" alt="">
                </div>
                <div class="top_info">
                    <div class="name">
                        名称test
                    </div>
                    <div class="message">
                        00
                    </div>
                    <div class="time">
                        <span style="margin-right: 20px;">2025-01-21 21:22 </span>
                        <span class="iconItem">
                            <svg-icon name="zan" width="20px" height="20px"></svg-icon>
                            <span>100</span>
                        </span>
                        <span class="iconItem">
                            <svg-icon name="no" width="20px" height="20px"></svg-icon>
                            <span>100</span>
                        </span>

                    </div>
                </div>
            </div>
            <div class="middle">
                <chatItem />
            </div>
            <div class="bottom">


            </div>
        </div>
    </div>

</template>

<script setup>
import { ref, onMounted } from 'vue'
import chatItem from './chatItem.vue'
const searchKeyword = ref('')
</script>


<style scoped lang="scss">
.search {
    display: flex;
    justify-content: space-between;
    align-items: center;

    // margin: 0 56px;
    .img {
        width: 48px;
        height: 48px;
        margin-right: 10px;

        img {
            width: 100%;
            height: 100%;
            border-radius: 50%;

        }
    }

    .search-input {
        flex: 1;
        position: relative;

        .but {
            position: absolute;
            right: 0;
            margin-top: 10px;
        }


    }
}

.main {
    min-height: 500px;
    margin-top: 20px;
    padding: 0 10px;

    .item {
        padding: 20px 0;
        border-bottom: 1px solid #ccc;

        .top {
            display: flex;

            .user_img {
                width: 48px;
                height: 48px;
                margin-right: 10px;

                img {
                    width: 100%;
                    height: 100%;
                    border-radius: 50%;
                }
            }

            .top_info {
                display: flex;
                flex-direction: column;
                justify-content: space-around;
                text-align: left;

                .name {
                    font-size: 14px;
                    color: #9499a0;


                }

                .message {
                    color: black;
                    font-size: 16px;
                }

                .time {
                    font-size: 13px;
                    color: #9499a0;

                    .iconItem {
                        margin-right: 20px;
                    }
                }
            }

        }
    }

}
</style>