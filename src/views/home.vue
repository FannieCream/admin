<template>
    <div id="home">
        <navbar/>

        <p>{{adminname}} 管理员你好</p>

        <div class="intro">
            <div class="intro-left">
<!--                <table width="400px" cellpadding="2px" cellspacing="2px 0">-->
<!--                    <tr><td class="intro-item">课程导入</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                    <tr><td class="intro-item">学生导入</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                    <tr><td class="intro-item">培养计划</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                    <tr><td class="intro-item">数据分析</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                </table>-->
                <div class="intro-one" v-for="one in intro_left_list">
                    <div class="intro-item">
                       * {{one.item}} *
                    </div>
                    <div class="triangle"></div>
                    <div class="intro-content">
                        {{one.content}}
                    </div>
                </div>
            </div>

            <div class="intro-right">
<!--                <table width="400px" cellpadding="2px" cellspacing="2px 0">-->
<!--                    <tr><td class="intro-item">课程管理</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                    <tr><td class="intro-item">学生管理</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                    <tr><td class="intro-item">班级管理</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                    <tr><td class="intro-item">管理员</td></tr>-->
<!--                    <tr><td class="intro-content">功能介绍</td></tr>-->
<!--                </table>-->
                <div class="intro-one" v-for="one in intro_right_list">
                    <div class="intro-item">
                        * {{one.item}} *
                    </div>
                    <div class="triangle"></div>
                    <div class="intro-content">
                        {{one.content}}
                    </div>

                </div>
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
        },
        data(){
            return {
                adminname: "Kitty",
                intro_left_list: [
                    {   item: "课程导入", content: "功能介绍"},
                    {   item: "学生导入", content: "功能介绍"},
                    {   item: "培养计划", content: "功能介绍"},
                    {   item: "数据分析", content: "功能介绍"}
                ],
                intro_right_list: [
                    {   item: "课程管理", content: "功能介绍"},
                    {   item: "学生管理", content: "功能介绍"},
                    {   item: "班级管理", content: "功能介绍"},
                    {   item: "管理员", content: "功能介绍"}
                ]
            }
        }
    }
</script>

<style lang="less" scoped>
    /*#home {*/
    /*    !*position: fixed;*!*/
    /*    width: 100%;*/
    /*    height: 1100px;*/
    /*    background: url("../assets/bgperson2.png") no-repeat center center;*/
    /*    background-size: cover;*/
    /*}*/
    p {
        /*font-size: 18px;*/
        position: relative;
        top:90px;
        left: 200px;
        font-size: 16px;
        color: #8a6d3b;
        /*color: red;*/
    }

    .intro {
        margin: auto;
        width:900px;
        position: relative;
        top:120px;
    }

    .intro-one {
        border-radius: 10px ;

        // 添加阴影
        -webkit-box-shadow: #ccc 0px 0px 20px;
        -moz-box-shadow: #ccc 0px 0px 20px;
        box-shadow: #ccc 0px 0px 20px;
    }
    .intro-one:hover {
        -webkit-box-shadow: #666 0px 0px 60px;
        -moz-box-shadow: #666 0px 0px 60px;
        box-shadow: #666 0px 0px 60px;

    }

    .intro-left {
        float: left;
    }

    .intro-right {
        float: right;
    }

    .intro-item {
        width: 400px;
        text-align: left;
        padding: 0 0 0 10px;
        height:60px;
        line-height: 60px;
        /*border: 1px solid black;*/
        border-radius: 10px 10px 0 0;
        background-color: #70AD47;
        color: white;
        font-weight: bolder;
        position: relative;
        /*top: 200px;*/
        z-index: 5;
        font-size: 14px;
    }

    .intro-content {
        width: 400px;
        text-align: center;
        height:180px;
        line-height: 180px;
        margin-top:-50px;
        background-color: #EEF7E9;
        margin-bottom: 50px;
        border-radius: 0 0 10px 10px;
        position: relative;
        z-index:1;
        /*background-color: #D1EEEE;*/
    }

    .triangle {
        width: 0;
        height: 0;
        border-width: 20px;
        border-style: solid;
        border-color: #70AD47 transparent transparent transparent;
        /*margin-top: -150px;*/
        position: relative;
        z-index:100;
    }



</style>