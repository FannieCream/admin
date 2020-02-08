<template>
    <div class="single">
        <table>
            <tr>
                <td>名称</td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>代码</td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>老师</td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>时间</td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>选修/必修</td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>校区</td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>课程内容</td>
                <td><input v-model="name"></td>
            </tr>
        </table>
        <button type="submit" style="float: right; margin-top:10px ">确认</button>

    </div>
</template>

<script>
    export default {
        name: "single"
    }
</script>

<style lang="less" scoped>
    .single {
        position: absolute;
        left: 40%;

        td {
            text-align: center;
        }
    }

</style>