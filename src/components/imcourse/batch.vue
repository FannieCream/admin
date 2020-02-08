<template>
    <div class="batch">
        <p style="text-align: center; width: 100%" >
            批量导入 <input type="text" placeholder=" 请输入 ... "> 添加文件
        </p>

        <img src="public/static/imcourse-example.PNG" style="width: 50%;margin-top: 50px">

        <p class="note-left">
            {{note1}}
        </p>
        <p class="note-right">
                {{note2}}
        </p>

    </div>
</template>

<script>
    export default {
        name: "batch",
        data() {
            return {
                note1: "请添加文件遵循上图格式",
                note2: "表格中有且仅有依次类别，课程代码，名称，开始时间，结束时间,校区，地点，内容介绍，选课人数上限，学分，必修/选修，模块"
            }
        }
    }
</script>

<style lang="less" scoped>
    .note-left {
        float: left;
        position: absolute;
        left: 30%;
        margin-top: 50px;
        /*margin-left: 100px;*/
        /*display: inline-block;*/
        font-size: 14px;
    }

    .note-right {
        width:420px;
        float: right;
        position: absolute;
        right: 10%;
        margin-top: 50px;
        font-size: 14px;
        /*marin-righ: 50px;*/
        /*display: inline-block;*/
    }


</style>