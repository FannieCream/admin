<template>
    <div>
        <navbar/>

        <p>XXX,管理员你好</p>

        <div class="intro">
            <div class="intro-left">
                <table width="400px" cellpadding="2px" cellspacing="2px 0">
                    <tr><td class="intro-item">课程导入</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                    <tr><td class="intro-item">学生导入</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                    <tr><td class="intro-item">培养计划</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                    <tr><td class="intro-item">数据分析</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                </table>
            </div>

            <div class="intro-right">
                <table width="400px" cellpadding="2px" cellspacing="2px 0">
                    <tr><td class="intro-item">课程管理</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                    <tr><td class="intro-item">学生管理</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                    <tr><td class="intro-item">班级管理</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                    <tr><td class="intro-item">管理员</td></tr>
                    <tr><td class="intro-content">功能介绍</td></tr>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
    import navbar from "@/components/navbar/index"
    export default {
        name: "home",
        components: {
            navbar
        }
    }
</script>

<style lang="less" scoped>
    p {
        /*font-size: 18px;*/
        position: relative;
        top:90px;
        /*color: red;*/
    }

    .intro {
        margin: auto;
        width:900px;
        position: relative;
        top:100px;
    }

    .intro td {
        border: 1px dashed black;
    }

    .intro-left {
        float: left;
    }

    .intro-right {
        float: right;
    }

    .intro-item {
        text-align: left;
        height:30px;
    }

    .intro-content {
        text-align: center;
        height:100px;
        margin-top:0;

    }


</style>