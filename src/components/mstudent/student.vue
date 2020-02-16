<template>
    <div>
        <div class="search-student">
            <p>检索</p>
            <table>
                <tr>
                    <td>学生</td>
                    <td>学号</td>
                    <td>年级</td>
                    <td>一级学院</td>
                    <td>班级</td>
                    <td>入党状态</td>
                    <td>计划达成</td>
                </tr>
                <tr>
                    <td><input type="text"></td>
                    <td><input type="text"></td>
                    <td><input type="text"></td>
                    <td><input type="text"></td>
                    <td><input type="text"></td>
                    <td><input type="text"></td>
                    <td><input type="text"></td>
                </tr>
            </table>
            <button type="submit">确认</button>
        </div>
        <div class="show-student">
            <table class="table table-bordered">
                <thead>
                <tr>
                    <td>学生</td>
                    <td>学号</td>
                    <td>年级</td>
                    <td>一级学院</td>
                    <td>班级</td>
                    <td>入党状态</td>
                    <td>计划达成</td>
                    <td>缺勤次数</td>
                    <td>删除</td>
                </tr>
                </thead>
                <tbody>
                <tr v-for="(stu,index) in studentlist">
                    <td>{{stu.sname}}</td>
                    <td>{{stu.snumber}}</td>
                    <td>{{stu.grade}}</td>
                    <td>{{stu.college}}</td>
                    <td>{{stu.class}}</td>
                    <td>{{stu.status}}</td>
                    <td>{{stu.finished}}</td>
                    <td>{{stu.absence}}</td>
                    <td><button @click="removeInfo(index)" type="button" class="btn btn-primary">点击</button></td>
                </tr>
                </tbody>
            </table>
            <button type="button" class="btn btn-default" style="position: relative; left: 40%">导出</button>
            <button type="button" class="btn btn-default" style="position: relative; left: 60%">确认</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "student",
        data() {
            return {
                studentlist: [
                    {sname:"小明", snumber:"1010", grade:"大一", college:"软件工程", class:"1班", status:1, finished:"3/5", absence:0},
                    {sname:"韩梅梅", snumber:"3011", grade:"大三", college:"软件工程", class:"1班", status:1, finished:"1/5", absence:0},
                    {sname:"李华", snumber:"2011", grade:"大一", college:"软件工程", class:"2班", status:3, finished:"3/10", absence:0}
                ]
            }
        },
        methods:{
            removeInfo(index){
                this.studentlist.splice(index,1)
                console.log(index)
                console.log(this.studentlist[index])
            }
        }

    }
</script>

<style lang="less" scoped>
    .search-student {
        border:2px solid red;
        /*width: 100%;*/
        text-align: center;

        p {
            float: left;
            border:1px solid #2e6da4;
        }

        button {
            float: right;
        }

        input {
            width: 100px;
        }

        td {
            padding: 0;
        }
    }

    .show-student {
        margin-top: 100px;
        margin-left: 200px;

        td {
            padding: 5px 20px;
            text-align: center;
        }
    }

</style>