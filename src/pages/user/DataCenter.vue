<template>
    <!--数据中心-->
    <div style="margin:0.5rem;overflow: auto;">
        <div class="work-title">数据概览 </div>
        <div class="header">
            <div class="left">
                <el-popover placement="right" title="提示" :width="400" trigger="hover" :content="content">
                    <template #reference>
                        <el-button type="text">
                            核心数据概览
                            <el-icon class="el-icon--right">
                                <WarningFilled />
                            </el-icon>
                        </el-button>

                    </template>
                </el-popover>

            </div>
            <div class="right">
                <div class="select-time">
                    <span class="sel_title">时间选择:</span>

                    <el-select v-model="model" placeholder="">
                        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
                        </el-option>
                    </el-select>
                </div>

                <div>
                    <el-button type="text" icon="UploadFilled">导出数据</el-button>
                </div>

            </div>
        </div>
        <div class="tags">
            <div :class="['item', { active: active == i }]" v-for="(item, i) in option_tags" :key="i"
                @click="() => active = i">
                <span class="name">{{ item.name }}</span>
                <span class="number"> {{ item.value }}</span>
            </div>
        </div>
        <div class="echarts" ref="echart">

        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from "vue"
import { WarningFilled } from '@element-plus/icons-vue'
import * as echarts from "echarts"
const content = ref(`
    1.每天中午12点更新前一日数据。第一次发布稿件后，将从次日开始生产数据。\n
    2.每项指标可查看所选时间范围内的增量、与上一周期的环比情况和历史累计总量。\n
    3.净增粉丝数=关注粉丝数-取消关注的粉丝数
`)

const model = ref('1')

const options = [
    {
        value: '1',
        label: '最近一周'
    },
    {
        value: '2',
        label: '最近一个月'
    },
    {
        value: '3',
        label: '最近三个月'
    },
    {
        value: '4',
        label: '最近半年'
    },
    {
        value: '5',
        label: '最近一年'
    }
]

const option_tags = ref([
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
    { name: '播放量', value: 0 },
])

const active = ref(0)

const echart = ref(null)
const option = {
    title: {
        text: '最近一周播放量',
        top: 10,
        left: 20
    },
    xAxis: {
        type: 'category',
        data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
    },
    yAxis: {
        type: 'value'
    },
    series: [
        {
            data: [150, 230, 224, 218, 135, 147, 260],
            type: 'line'
        }
    ]
};
const ec = ref({})

onMounted(() => {
    //初始化echarts
    ec.value = echarts.init(echart.value);
    ec.value.setOption(option);

})

</script>

<style lang="scss" scoped>
.work-title {
    font-weight: 600;
    font-size: 1.5rem;
}

::v-deep.el-button--text {
    color: #302e2e;
}

.header {
    display: flex;
    justify-content: space-between;
    margin: 10px 56px;

    .right {
        display: flex;
        align-items: center;
        justify-content: space-around;

        .select-time {
            display: flex;

            width: 200px;
            margin-right: 20px;

            .sel_title {
                display: inline-block;
                width: 100px;
                height: 32px;
                line-height: 32px;
            }
        }
    }
}

.tags {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    align-items: center;

    .item {
        width: 200px;
        height: 60px;
        border-radius: 10px;
        background-color: #fafafa;
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin: 10px;

        &:hover {
            background-color: #e6e6e6;
        }
    }

    .active {
        background-color: pink;
    }


}

.echarts {
    width: 800px;
    height: 600px;
    margin: auto;
    border: 1px solid #ccc;
    // background-color: pink;
    border-radius: 10px;
}
</style>