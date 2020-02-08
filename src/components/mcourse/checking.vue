<template>
    <div class="checking">
        <div class="show-course" v-for="item in courselist">
            <table>
                <tr>
                    <td>课程名称：{{item.cname}}</td>
                    <td>课程代码：{{item.code}}</td>
                    <td>授课老师：{{item.teacher}}</td>
                    <td>类型：{{item.ctype}}</td>
                </tr>
                <tr>
                    <td>校区：{{item.district}}</td>
                    <td>地点：{{item.place}}</td>
                    <td>时间：{{item.time}}</td>
                    <td>课程内容：{{item.content}}</td>
                </tr>
            </table>
        </div>
        <div class="show-student">
            <table class="table table-bordered">
                <thead>
                <tr>
                    <td>序号</td>
                    <td>学生</td>
                    <td>学号</td>
                    <td>年级</td>
                    <td>一级学院</td>
                    <td>缺勤次数</td>
                    <td>删去</td>
                </tr>
                </thead>
                <tbody>
                <tr v-for="stu in studentlist">
                    <td>{{stu.sid}}</td>
                    <td>{{stu.sname}}</td>
                    <td>{{stu.snumber}}</td>
                    <td>{{stu.grade}}</td>
                    <td>{{stu.college}}</td>
                    <td>{{stu.absence}}</td>
                    <td><button type="button" class="btn btn-primary">点击</button></td>
                </tr>
                </tbody>

            </table>
            <button type="button" class="btn btn-default" style="display: inline-block; margin-left: 5%; margin-right: 20%">确认</button>
            <button type="button" class="btn btn-default" style="display: inline-block">导入考勤名单</button>

        </div>
    </div>
</template>

<script>
    export default {
        name: "checking",
        data() {
            return {
                courselist: [
                    {   cname:"课程1", code:"1001", teacher: "李老师", time:"1.1",
                        district:"中北校区", place:"文史楼101", ctype:"选修", content:"这是课程内容描述" }
                ],

                studentlist: [
                    {   sid:1, sname:"小明", snumber:"10191111111", grade:"大一",  college:"软件工程", absence:2    },
                    {   sid:2, sname:"二明", snumber:"10181111112", grade:"大二",  college:"软件工程", absence:0    },
                    {   sid:3, sname:"三明", snumber:"10191111113", grade:"大一",  college:"软件工程", absence:2    },
                    {   sid:4, sname:"大明", snumber:"10171111114", grade:"大三",  college:"软件工程", absence:0    },
                    {   sid:5, sname:"小小明", snumber:"10191111115", grade:"大一",  college:"软件工程", absence:1    }
                ]
            }
        }
    }
</script>

<style lang="less" scoped>
    .show-course table td{
        text-align: left;
        padding: 5px 30px;
        position: relative;
        left: 40%;

    }

    .show-student {
        margin-top: 50px;
        margin-bottom: 50px;
    }

    .show-student table td {
        max-width: 50px;
        vertical-align: center;
        text-align: center;
        padding: 5px 10px;
        /*position: relative;*/
        /*left: 10%;*/
    }


</style>