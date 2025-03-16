<template>
    <div class="content-item" @click="goToContent">
        <div class="content-item-left">
            <div class="content-item-left-top">
                <p class="title">高中化学工艺流程答题规律，实在不会赶紧抄吧</p>
            </div>
            <div class="content-item-left-middle">
                最近有高二的同学给我留言说化学成绩不是很好，现在复习到化学工艺流程的板块，不知道怎么分析问题，答不出来，该怎么办？
            </div>
            <div class="content-item-left-bottom">
                <div class="img_box">
                    <img src="@/assets/img/user.webp" alt="">
                    <span class="name">奶糖团子01</span>
                </div>
                <div class="tag">日常</div>
                <div class="option">
                    <div class="option_item">
                        <el-icon>
                            <View />
                        </el-icon>
                        <span class="viewCount">2.0万</span>
                    </div>
                    <div class="option_item">
                        <svg-icon name="zan" width="20px" height="20px" color="pink"></svg-icon>

                        <span class="zanCount">903</span>
                    </div>
                    <div class="option_item">
                        <el-icon>
                            <ChatDotSquare />
                        </el-icon>
                        <span class="messageCount">1068</span>
                    </div>

                </div>

            </div>
        </div>
        <div class="content-item-right">
            <img src="@/assets/img/right.webp" alt="">
        </div>
    </div>
</template>

<script setup>
import { useRouter } from "vue-router"

const router = useRouter()
const goToContent = () => {
    router.push('/content')
}
</script>
<style scoped lang="scss">
.content-item {
    width: 100%;
    padding: 20px 0;
    height: 128px;
    box-sizing: border-box;
    border-bottom: 1px solid #E3E5E7;
    display: flex;
    cursor: pointer;

    &:hover .title {
        color: #0fb7ef;
    }

    .content-item-left {
        width: 543px;
        color: #9499a0;

        .content-item-left-top {
            font-size: 20px;
            color: black;
            line-height: 26px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            transition: color .3s;
            text-align: left;

            // .title {
            //     &:hover {
            //         color: #0fb7ef;
            //     }
            // }

        }

        .content-item-left-middle {
            margin-top: 4px;
            color: #9499a0;
            font-size: 12px;
            letter-spacing: 0;
            line-height: 22px;
            text-overflow: ellipsis;
            overflow: hidden;
            white-space: nowrap;

        }

        .content-item-left-bottom {
            display: flex;
            margin-top: 10px;
            align-items: center;

            .img_box {
                img {
                    width: 24px;
                    height: 24px;
                    margin-right: 10px;
                    border-radius: 50%;
                }

                display: flex;
                align-items: center;
            }

            .tag {
                margin: 0 20px;
            }

            .option {
                display: flex;
                width: 222px;
                justify-content: space-around;

                .option_item {
                    display: flex;
                    align-items: center;

                    // width: 40px;
                    span {
                        margin-left: 10px;
                    }
                }
            }

        }
    }

    .content-item-right {
        margin-left: 20px;
        width: 117px;
        height: 88px;

        img {
            width: 100%;
            height: 100%;
        }
    }
}
</style>