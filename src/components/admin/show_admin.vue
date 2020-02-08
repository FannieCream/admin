<template>
    <div class="show-admin">
        <table class="table table-bordered">
            <thead>
            <tr>
                <td>序号</td>
                <td>用户名</td>
                <td>姓名</td>
                <td>工号/学号</td>
                <td>密码</td>
                <td>级别</td>
                <td>删除</td>
            </tr>
            </thead>
            <tbody>
            <tr v-for="one in adminlist">
                <td>{{one.sid}}</td>
                <td>{{one.username}}</td>
                <td>{{one.name}}</td>
                <td>{{one.number}}</td>
                <td>{{one.pwd}}</td>
                <td>{{one.grade}}</td>
                <td><button type="button" class="btn btn-primary">点击</button></td>
            </tr>
            </tbody>
        </table>
        <button type="button" class="btn btn-default" style="position: relative; left: 60%">添加</button>
        <button type="button" class="btn btn-default" style="position: relative; left: 90%">确定</button>
    </div>
</template>

<script>
    export default {
        name: "show_admin",
        data() {
            return {
                adminlist: [
                    {   sid:1, username:"Alex", name:"刘老师", number:"50115023", pwd:"111", grade:"1" },
                    {   sid:2, username:"Eric", name:"唐老师", number:"30415023", pwd:"1114", grade:"3" },
                    {   sid:3, username:"Ben", name:"李老师", number:"10115023", pwd:"1115", grade:"2" }
                ]
            }
        }
    }
</script>

<style lang="less" scoped>
    .show-admin {
        td {
            padding: 5px 30px;
            text-align: center;
        }
    }

</style>