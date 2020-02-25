<template>
    <div class="batch">
        <table style="margin: 0 auto;width:200px">
            <tr>
                <td>班级选择</td>
                <td><select_class></select_class></td>
            </tr>
        </table>
        <table class="choose-file">
            <tr>
                <td>批量导入</td>
                <td><input type="text" placeholder=" 请输入 ... "></td>
                <td><input type="file" style="color: transparent;"></td>
            </tr>
        </table>


<!--        <p style="text-align: center; width: 100%" >-->
<!--            批量导入 <input type="text" placeholder=" 请输入 ... ">-->
<!--            <input type="file" style="color: transparent;">-->
<!--        </p>-->

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
    import select_class from "./select_class";
    export default {
        name: "batch",
        components: {
            select_class
        },

        data() {
            return {
                note1: "请添加文件遵循上图格式",
                note2: "表格中有且仅有依次类别: 学号，姓名，入党状态，一级学院"
            }
        }
    }
</script>

<style lang="less" scoped>
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