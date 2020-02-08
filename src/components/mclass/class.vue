<template>
    <div>
        <div class="search-class">
            <div class="search-text">
                <p>检索</p>
            </div>
            <div class="search-table">
                <table>
                    <tr>
                        <td>班级名称</td>
                        <td>班级描述</td>
                        <td>开班时间</td>
                        <td>结课时间</td>
                        <td>班级状态</td>
                    </tr>
                    <tr>
                        <td><input type="text" name="class-name"></td>
                        <td><input type="text" name="class-content"></td>
                        <td><input type="text" name="class-begin"></td>
                        <td><input type="text" name="class-end"></td>
                        <td><input type="text" name="class-status"></td>
                    </tr>
                </table>
            </div>
            <div class="search-btn">
                <button type="submit" class="btn btn-default">确认</button>
            </div>
        </div>

        <div class="class-info">
            <table class="table table-bordered">
                <thead>
                <tr>
                    <td>班级名称</td>
                    <td>班级描述</td>
                    <td>开班时间</td>
                    <td>结课时间</td>
                    <td>班级状态</td>
                    <td>班级名单</td>
                    <td>删除</td>
                </tr>
                </thead>
                <tbody>
                <tr v-for="one in classlist">
                    <td>{{one.name}}</td>
                    <td>{{one.description}}</td>
                    <td>{{one.begin}}</td>
                    <td>{{one.end}}</td>
                    <td>{{one.status}}</td>
                    <td><button class="btn btn-primary">点击</button></td>
                    <td><button class="btn btn-primary">点击</button></td>
                </tr>
                </tbody>
            </table>
            <button type="submit" class="btn btn-default">确认</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "classlist",
        data(){
            return {
                classlist:[
                    {   name:"青马（1）班", description:"针对17级同学", begin:"19年春季", end:"19年秋季", status:"活跃"   },
                    {   name:"青马（2）班", description:"针对17级同学", begin:"19年秋季", end:"20年春季", status:"不活跃"   },
                    {   name:"青马（3）班", description:"针对18级同学", begin:"19年春季", end:"19年秋季", status:"活跃"   },
                    {   name:"青马（4）班", description:"针对17,18级同学", begin:"20年春季", end:"20年秋季", status:"活跃"   },
                    {   name:"青马（5）班", description:"针对19级同学", begin:"19年春季", end:"19年秋季", status:"不活跃"   }
                ]
            }
        }
    }
</script>

<style lang="less" scoped>
    .search-class {
        border:2px solid red;
        text-align: center;

        .search-text {
            /*float: left;*/
            /*position: absolute;*/
            /*top:50%;*/
            /*left:-20%;*/
            display: inline-block;
            margin-right: 50px;
        }

        .search-table {
            display: inline-block;
        }

        input {
            width:100px;
        }

        td {
            text-align: center;
        }

        .search-btn {
            /*float: right;*/
            /*position: absolute;*/
            /*top:50%;*/
            /*right:-20%;*/
            display: inline-block;
            margin-left: 50px;
        }
    }

    .class-info {
        margin-top: 50px;
        text-align: center;
        margin-bottom: 50px;

    }

</style>