<template>
    <div>
        <div class="show-class-info">
            <table>
            <tr>
                <td>班级信息：{{info}}</td>
                <td>班级描述：{{description}}</td>
            </tr>
            <tr>
                <td>开班时间：{{begin}}</td>
                <td>结课时间：{{end}}</td>
                <td>班级活跃度：{{status}}</td>
            </tr>
            </table>
        </div>

        <div class="student-info">
            <table class="table table-bordered">
                <thead>
                <tr>
                    <td>序号</td>
                    <td>学生</td>
                    <td>学号</td>
                    <td>年级</td>
                    <td>一级学院</td>
                    <td>入党状态</td>
                    <td>班级转移</td>
                </tr>
                </thead>
                <tbody>
                <tr v-for="one in students">
                    <td>{{one.sid}}</td>
                    <td>{{one.sname}}</td>
                    <td>{{one.snumber}}</td>
                    <td>{{one.grade}}</td>
                    <td>{{one.college}}</td>
                    <td>{{one.status}}</td>
                    <td><select_class></select_class></td>
                </tr>
                </tbody>
            </table>

            <button class="btn btn-primary" style="margin-left:50px">确认</button>
            <button class="btn btn-primary" style="margin-left:50px">导入考勤名单</button>
        </div>
    </div>
</template>

<script>
    import select_class from "../imstudent/select_class";
    export default {
        name: "studentlist",
        components: {
            select_class
        },
        data() {
            return {
                info:"青马班（1）班",
                description:"针对17级开放",
                begin: "19年春季",
                end:"19年秋季",
                status:"活跃",

                students: [
                    {   sid:1, sname:"小明", snumber:"50112034", grade:"大三", college:"设计学院", status:"预备党员"    },
                    {   sid:2, sname:"小明", snumber:"50112034", grade:"大三", college:"设计学院", status:"预备党员"    },
                    {   sid:3, sname:"小明", snumber:"50112034", grade:"大三", college:"设计学院", status:"预备党员"    },
                    {   sid:4, sname:"小明", snumber:"50112034", grade:"大三", college:"设计学院", status:"预备党员"    },
                    {   sid:5, sname:"小明", snumber:"50112034", grade:"大三", college:"设计学院", status:"积极分子"    }
                ]
            }
        }
    }
</script>

<style lang="less" scoped>
    .show-class-info {
        td {
            width: 200px;
            text-align: left;
            padding: 5px;

        }

    }

    .student-info {
        margin-top: 50px;
        margin-bottom: 50px;
        text-align: center;

    }

</style>