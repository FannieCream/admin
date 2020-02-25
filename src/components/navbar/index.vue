<template>
    <div id="mynavbar">
        <nav>
            <ul>
<!--                <li><router-link to="/home">主页</router-link></li>-->
<!--                <li><router-link to="/imcourse">课程导入</router-link></li>-->
<!--                <li><router-link to="/mcourse">课程管理</router-link></li>-->
<!--                <li><router-link to="/mclass">班级管理</router-link></li>-->
<!--                <li><router-link to="/imstudent">学生导入</router-link></li>-->
<!--                <li><router-link to="/mstudent">学生管理</router-link></li>-->
<!--                <li><router-link to="/plan">培养计划</router-link></li>-->
<!--                <li><router-link to="/data">数据分析</router-link></li>-->
<!--                <li><router-link to="/admin">管理员</router-link></li>-->
                <li  v-for="(item,index) in headerlist" >
                    <router-link :to="item.path" exact-active-class="route-link-exact-active">
                        {{item.title}}
                    </router-link>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "navbar",
        data() {
            return {
                headerlist: [
                    {id: "1", path: "/home", title: "主页"},
                    {id: "2", path: "/imcourse", title: "课程导入"},
                    {id: "3", path: "/mcourse", title: "课程管理"},
                    {id: "4", path: "/mclass", title: "班级管理"},
                    {id: "5", path: "/imstudent", title: "学生导入"},
                    {id: "6", path: "/mstudent", title: "学生管理"},
                    {id: "7", path: "/plan", title: "培养计划"},
                    {id: "8", path: "/data", title: "数据分析"},
                    {id: "9", path: "/admin", title: "管理员"},
                ],

            }
        }
    }
</script>



<style lang="less" scoped>
    #mynavbar {
        /*background-color: black;*/
        background: url("../../assets/green2.png") repeat-x;
        position: absolute;
        height:60px;
        line-height: 60px;
        width: 100% ;
        top:0;
        font-size: 16px;
        text-align: center;

        li{
            width:120px;
            height: 30px;
            line-height: 30px;
            display: inline-block;
            vertical-align: center;
        }

        a{
            color: black;
        }

        .route-link-exact-active{
            /*width:120px;*/
            /*height: 30px;*/
            /*background-color: #95B3FB;*/
            color: darkgreen;
            border-bottom:1px solid darkgreen;
            font-weight: bolder;

        }








    }



</style>