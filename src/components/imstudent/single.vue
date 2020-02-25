<template>
    <div class="single">
        <form>
        <table>
            <tr>
                <td class="item">学生 </td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">学号 </td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">年级 </td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">一级学院 </td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">入党状态 </td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">班级 </td>
                <td><select_class></select_class></td>
            </tr>
        </table>
        </form>
        <button type="submit" class="btn btn-success" style="margin: 30px 0 auto">确认</button>

    </div>
</template>

<script>
    import select_class from "./select_class";
    export default {
        name: "single",
        components: {
            select_class
        }
    }
</script>

<style lang="less" scoped>
    .single {
        /*position: absolute;*/
        /*left: 40%;*/
        width: 450px;
        height: 400px;
        /*border: 2px solid black;*/
        margin: 0 auto;
        margin-bottom: 100px;
        border-radius: 10px;
        background-color: #F6F6F6;
        /*background-color: #C1FFC1;*/
        padding: 20px;

        table {
            /*height: 300px;*/
            /*line-height: 300px;*/
            text-align: center;
            margin: 0 auto;
            margin-top: 20px;
        }

        tr{
            /*border: 2px solid red;*/
            margin-bottom: 20px;
            height:40px;
        }

        .item {
            text-align: center;
            width: 80px;
            font-size: 16px;
            color: darkgreen;
            font-weight: bold;
        }

        input[type=text],select,textarea {
            padding: 0 10px;
            width: 200px;
            height: 30px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }


    }

</style>