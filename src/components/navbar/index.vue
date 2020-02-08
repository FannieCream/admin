<template>
    <div class="navbar">
        <nav>
            <ul>
                <li><router-link to="/home">主页</router-link></li>
                <li><router-link to="/imcourse">课程导入</router-link></li>
                <li><router-link to="/mcourse">课程管理</router-link></li>
                <li><router-link to="/mclass">班级管理</router-link></li>
                <li><router-link to="/imstudent">学生导入</router-link></li>
                <li><router-link to="/mstudent">学生管理</router-link></li>
                <li><router-link to="/plan">培养计划</router-link></li>
                <li><router-link to="/data">数据分析</router-link></li>
                <li><router-link to="/admin">管理员</router-link></li>
<!--                <li v-for="list in headerlist": key="list.id">-->
<!--                    <router-link to="{name: list.name}">-->
<!--                        {{list.title}}-->
<!--                    </router-link>-->
<!--                </li>-->
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "navbar",
        data() {
            return {
                // headerlist: [
                //     {id: "1", name: "home", title: "主页"},
                //     {id: "2", name: "imcourse", title: "主页"},
                //     {id: "3", name: "mcourse", title: "主页"},
                //     {id: "4", name: "mclass", title: "主页"},
                //     {id: "5", name: "imstudent", title: "主页"},
                //     {id: "6", name: "mstudent", title: "主页"},
                //     {id: "7", name: "plan", title: "主页"},
                //     {id: "8", name: "data", title: "主页"},
                //     {id: "9", name: "admin", title: "主页"},
                // ],
                // isShow: false
            }
        }
    }
</script>

<style lang="less" scoped>
    .navbar {
        background-color: black;
        position: absolute;
        height:50px;
        line-height: 50px;
        width: 100% ;
        top:0;
        font-size: 16px;
    }

    .navbar li {
        width:120px;
        height: 30px;
        line-height: 30px;
        /*list-style: none;*/
        display: inline-block;
        text-align: center;
        border: 2px solid red;
        vertical-align: center;
        color:white;
    }

    .navbar active {
        color:red;

    }


</style>