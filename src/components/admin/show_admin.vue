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
            <tr v-for="(one,index) in adminlist">
                <td>{{index+1}}</td>
                <td>{{one.username}}</td>
                <td>{{one.name}}</td>
                <td>{{one.number}}</td>
                <td>{{one.pwd}}</td>
                <td>{{one.grade}}</td>
                <td><button @click="removeInfo(index)" type="button" class="btn btn-primary">点击</button></td>
            </tr>
            <tr  v-show="seen">
                <td><input type="text" v-model="newAdmin.sid"></td>
                <td><input type="text" v-model="newAdmin.username"></td>
                <td><input type="text" v-model="newAdmin.name"></td>
                <td><input type="text" v-model="newAdmin.number"></td>
                <td><input type="text" v-model="newAdmin.pwd"></td>
                <td><input type="number" v-model="newAdmin.grade"></td>
            </tr>
            </tbody>
        </table>

<!--        <fieldset v-show="seen" >-->
<!--&lt;!&ndash;             <legend>新增用户</legend>&ndash;&gt;-->
<!--             <div class="addPart">-->
<!--             <table>-->
<!--                <tr>-->
<!--                    <td><label>序号：</label></td>-->
<!--                    <td><input type="text" v-model="newAdmin.sid"></td>-->
<!--                </tr>-->
<!--                <tr>-->
<!--                    <td><label>用户名：</label></td>-->
<!--                    <td><input type="text" v-model="newAdmin.username"></td>-->
<!--                </tr>-->
<!--                <tr>-->
<!--                    <td><label>姓名：</label></td>-->
<!--                    <td><input type="text" v-model="newAdmin.name"></td>-->
<!--                </tr>-->
<!--                 <tr>-->
<!--                      <td><label>工号/学号：</label></td>-->
<!--                      <td><input type="text" v-model="newAdmin.number"></td>-->
<!--                 </tr>-->
<!--                 <tr>-->
<!--                      <td><label>密码：</label></td>-->
<!--                      <td><input type="text" v-model="newAdmin.pwd"></td>-->
<!--                 </tr>-->
<!--                 <tr>-->
<!--                      <td><label>级别：</label></td>-->
<!--                      <td><input type="number" v-model="newAdmin.grade"></td>-->
<!--                 </tr>-->
<!--        </table>-->

<!--        </div> -->
<!--        </fieldset>-->

        <button @click="addInfo" type="button" class="btn btn-default" >添加</button>
        <button @click="submitInfo" type="button" class="btn btn-default">确定</button>
    </div>
</template>

<script>
    export default {
        name: "show_admin",
        data() {
            return {

                seen: false,
                adminlist: [
                    {   sid:1, username:"Alex", name:"刘老师", number:"50115023", pwd:"111", grade:"1" },
                    {   sid:2, username:"Eric", name:"唐老师", number:"30415023", pwd:"1114", grade:"3" },
                    {   sid:3, username:"Ben", name:"李老师", number:"10115023", pwd:"1115", grade:"2" },
                    {   sid:4, username:"Ben", name:"李老师", number:"10115023", pwd:"1115", grade:"2" },
                    {   sid:5, username:"Ben", name:"李老师", number:"10115023", pwd:"1115", grade:"2" },
                ],

                newAdmin:{
                    sid:"" ,
                    username: "",
                    name: "",
                    number: "",
                    pwd: "",
                    grade: ""
                }

            }
        },

        methods:{
            removeInfo(index){
                this.adminlist.splice(index,1)
                console.log(index)
                console.log(this.adminlist[index])
            },

            addInfo: function () {
                this.seen = this.seen == false ? true : false
            },

            submitInfo: function () {
                this.adminlist.push(this.newAdmin)
                this.newAdmin = {}
                this.seen = false

            }
        }
    }
</script>

<style lang="less" scoped>
    .show-admin {
        text-align: center;

        td {
            padding: 5px 20px;
            /*text-align: center;*/
        }
    }

</style>