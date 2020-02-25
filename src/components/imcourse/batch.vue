<template>
    <div class="batch">
        <div>
            <table class="choose-file">
                <tr>
                    <td>批量导入</td>
                    <td><input type="text" placeholder=" 请输入 ... "></td>
                    <td><input type="file" style="color: transparent;"></td>
                </tr>
            </table>
        </div>

<!--        <img :src="imgURL" style="width: 50%;margin-top: 50px">-->
        <img src="../../assets/imcourse-example.png" style="width: 50%;margin-top: 50px">

        <p class="note-left">
            {{note1}}
        </p>
        <p class="note-right">
                {{note2}}
        </p>

    </div>
</template>

<script>
    // import imgURL from "../../assets/imcourse-example.png"
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

    .choose-file {
        position: relative;
        left:37%;

        td {
            padding: 5px;
        }

        input[type=text] {
            width: 200px;
            height: 30px;
        }
    }


</style>