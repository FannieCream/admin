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
            <button class="btn btn-warning" type="submit">确认</button>
        </div>

        <div class="show-student">
            <table class="table table-striped">
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
            <button type="button" class="btn btn-default" style="position: relative; left: 40%; margin-bottom: 50px">导出</button>
            <button type="button" class="btn btn-default" style="position: relative; left: 60%; margin-bottom: 50px">确认</button>
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
        /*border:2px solid red;*/
        width: 1000px;
        /*width: 100%;*/
        text-align: center;
        margin: 50px 0 auto;
        margin-left: 200px;

        p {
            float: left;
            /*border:1px solid #2e6da4;*/
            margin-top: 20px;
            margin-right: 30px;
            color: #2e6da4;
            font-size: 16px;
            font-weight: bold;
        }

        input[type=text] {
            width: 100px;
            height: 30px;
            padding: 0 5px;
        }

        button {
            float: right;
            margin-right: 50px;
            margin-top: -30px;
        }
    }

    .show-student {
        margin-top: 100px;

        .table-striped {
            margin-top: -30px;
            margin-bottom: 30px;

            thead {
                color: black;
                font-weight: bold;
                font-size: 16px;

                td {
                    height: 50px;
                    line-height: 50px;
                    background-color: #d0e9c6;
                    border: 1px solid darkgrey;
                }
            }

            td {
                width: 150px;
                height: 50px;
                line-height: 50px;
                padding: 5px;
                text-align: center;
                border: 1px solid darkgrey;
                /*max-width: 30px;*/
                /*width: 30px;*/
                white-space: nowrap;
                overflow: hidden;
                text-overflow:ellipsis;
            }
        }
    }
</style>