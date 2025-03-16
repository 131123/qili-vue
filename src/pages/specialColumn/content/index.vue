<template>
    <div class="bg">
        <div class="contentMain">
            <div class="header">
                <p>高中化学工艺流程答题规律，实在不会赶紧抄吧</p>
            </div>
            <div class="userInfo">
                <div class="left">
                    <div class="img">
                        <img src="@/assets/img/user.webp" alt="">
                    </div>
                    <div class="info">
                        <div class="name">
                            奶糖团子01
                        </div>
                        <div class="time">
                            2025年01月19日 17:10
                        </div>
                    </div>

                </div>
                <div class="right">
                    <el-icon>
                        <More />
                    </el-icon>
                </div>
            </div>
            <div class="content">
                暂无内容
            </div>
            <div class="tag">
                <tag />
            </div>
            <div class="message">
                <message />
            </div>


        </div>
        <div class="nav">
            <div class="item" @click="changeSvg(svg_type['zan'])">
                <!-- <el-icon size="20">
                    <Pointer />
                </el-icon> -->
                <svg-icon :name="svg_type['zan']" width="20px" height="20px"></svg-icon>
                <span>904</span>
            </div>
            <div class="item" @click="changeSvg(svg_type['star'])">
                <!-- <el-icon size="20">
                    <Star />
                </el-icon> -->
                <svg-icon :name="svg_type['star']" width="20px" height="20px"></svg-icon>
                <span>2019</span>
            </div>
            <div class="item">
                <el-icon size="20">
                    <Position />
                </el-icon>
                <span>123</span>
            </div>
            <div class="item">
                <el-icon size="20">
                    <ChatLineRound />
                </el-icon>
                <span>234</span>
            </div>
        </div>

    </div>

</template>

<script setup>
import tag from './tag.vue';
import message from './message.vue'
import { ref, onMounted, onUnmounted, watch, computed } from 'vue'
const svg_type = ref({
    zan: 'zan',
    star: 'star',

})
const changeSvg = (name) => {
    console.log(123, name);

    if (name.match(/active/)) {
        svg_type.value[name.split('_')[0]] = name.replace(/_active/g, '')
    } else {
        svg_type.value[name] = name + '_active'
    }
    console.log(svg_type);

}




</script>
<style scoped lang="scss">
.contentMain {
    position: absolute;
    width: 708px;
    height: calc(100vh - 108px);
    left: 50%;
    transform: translateX(-50%);
    top: 10px;
    background-color: #fff;
    box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    overflow: auto;
    scrollbar-width: none;
    /* 隐藏滚动条（Firefox） */
    -ms-overflow-style: none;

    /* 隐藏滚动条（IE 和 Edge） */
    &::-webkit-scrollbar {
        display: none;
        /* 隐藏滚动条 */
    }


    .header {
        color: black;
        font-size: 28px;
        font-weight: 700;
        line-height: 1.4;
        margin-top: 30px;
        text-align: center;
    }

    .userInfo {
        display: flex;
        justify-content: space-between;
        // width: 100%;
        height: 88px;
        padding: 20px 56px;

        .left {
            // width: 600px;
            display: flex;

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

            .info {
                text-align: left;

                .name {
                    color: black;
                    cursor: pointer;
                    font-size: 17px;
                    font-weight: 600;
                }

                .time {

                    color: #9499a0;
                    display: flex;
                    font-size: 13px;

                }
            }
        }

        .right {
            align-items: center;
            display: flex;
            flex-direction: row-reverse;
            flex-shrink: 0;
            height: 48px;
            min-width: 100px;
            position: relative;
            // transform: rotate(90deg);
        }
    }

    .content {
        min-height: 500px;
    }
}

.bg {
    width: 100vw;
    height: calc(100vh - 98px);
    background-image: url("@/assets/img/bg.png");
    position: relative;
}

.nav {
    position: fixed;

    transition: .5s ease-in-out;
    top: 280px;
    right: 50%;
    transform: translateX(415px);
    z-index: 9999;
    background-color: #fff;
    width: 58px;
    height: 298px;
    box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    font-size: 16px;
    color: #9499a0;

    .item {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        cursor: pointer;
        // &:hover {
        //     color: #34afec;

        // }
    }
}
</style>