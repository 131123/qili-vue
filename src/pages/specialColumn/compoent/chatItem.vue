<template>
    <div class="content">
        <div class="user_img">
            <img src="@/assets/img/user.webp" alt="">
        </div>
        <div class="info">
            <div class="name">
                <span>小小</span>回复<span>XXXXX</span>：
                <span class="messages">
                    很快就会大幅亏损的发货了
                </span>
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
</template>

<script setup>

</script>
<style scoped lang="scss">
.content {
    display: flex;
    margin: 5px 56px;

    .user_img {
        width: 28px;
        height: 28px;

        img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
        }
    }

    .info {
        display: flex;
        flex-direction: column;
        margin-left: 10px;
        justify-content: space-around;
        text-align: left;

        .time {
            font-size: 13px;
            color: #9499a0;

            .iconItem {
                margin-right: 20px;
            }
        }
    }
}
</style>