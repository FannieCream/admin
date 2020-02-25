<template>
    <div class="single">
        <form>
        <table>
            <tr>
                <td class="item">名称</td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">代码</td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">老师</td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">时间</td>
                <td><input type="text"></td>
            </tr>
            <tr>
                <td class="item">选修/必修</td>
                <td><select id="type" name="type">
                    <option value="min">选修</option>
                    <option value="zhong">必修</option>
                </select></td>
            </tr>
            <tr>
                <td class="item">校区</td>
                <td><select id="district" name="district">
                    <option value="min">闵行校区</option>
                    <option value="zhong">中山北路校区</option>
                </select></td>
            </tr>
            <tr>
                <td class="item">课程内容</td>
<!--                <td><input type="text" v-model="name"></td>-->
                <td><textarea></textarea></td>
            </tr>
        </table>
        </form>
        <button type="submit" class="btn btn-success" style="margin-top:20px; width: 120px;letter-spacing: 10px; text-align:center ">确认</button>
    </div>
</template>

<script>
    export default {
        name: "single"
    }
</script>

<style lang="less" scoped>
    .single {
        /*position: absolute;*/
        /*left: 40%;*/
        width: 450px;
        height: 450px;
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
        textarea {
            height: 80px;
        }

    }

</style>