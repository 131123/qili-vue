<script>
export default {
    name: "SvgIcon",
    props: {
        // 属性值前缀
        prefix: {
            type: String,
            default: '#icon-'
        },
        // 图标名称
        name: {
            type: String,
            default: ''
        },
        // 图标颜色
        color: {
            type: String,
            default: ''
        },
        // 图标宽度
        width: {
            type: String,
            default: ''
        },
        // 图标高度
        height: {
            type: String,
            default: ''
        }
    }
}
</script>

<template>
    <svg :style="{ width: width, height: height, color: color }">
        <use :xlink:href="prefix + name" :fill="color"></use>
    </svg>
</template>

<style scoped></style>
