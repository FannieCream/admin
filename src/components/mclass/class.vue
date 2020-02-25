<template>
    <div>
        <studentlist v-show="isChecking" :class="{'active':isCheckingActive}"></studentlist>
        <div class="search-class" v-show="isSearch" :class="{'active':isSearchActive}">
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
                <button type="submit" class="btn btn-warning">确认</button>
            </div>
        </div>

        <div class="class-info">
            <table class="table table-striped">
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
                <tr v-for="(one,index) in classlist">
                    <td>{{one.name}}</td>
                    <td>{{one.description}}</td>
                    <td>{{one.begin}}</td>
                    <td>{{one.end}}</td>
                    <td>{{one.status}}</td>
                    <td><button @click="showChecking" class="btn btn-primary">点击</button></td>
                    <td><button @click="removeInfo(index)"  class="btn btn-primary">点击</button></td>
                </tr>
                </tbody>
            </table>
            <button type="submit" class="btn btn-default" style="margin-top: 50px">确认</button>
        </div>
    </div>
</template>

<script>
    import studentlist from "./student"
    export default {
        name: "classlist",
        components: {
            studentlist
        },

        data(){
            return {
                isChecking: false,
                isCheckingActive: false,
                isSearch: true,
                isSearchActive: false,

                classlist:[
                    {   name:"青马（1）班", description:"针对17级同学", begin:"19年春季", end:"19年秋季", status:"活跃"   },
                    {   name:"青马（2）班", description:"针对17级同学", begin:"19年秋季", end:"20年春季", status:"不活跃"   },
                    {   name:"青马（3）班", description:"针对18级同学", begin:"19年春季", end:"19年秋季", status:"活跃"   },
                    {   name:"青马（4）班", description:"针对17,18级同学", begin:"20年春季", end:"20年秋季", status:"活跃"   },
                    {   name:"青马（5）班", description:"针对19级同学", begin:"19年春季", end:"19年秋季", status:"不活跃"   }
                ]
            }
        },

        methods:{
            removeInfo(index){
                this.classlist.splice(index,1)
                console.log(index)
                console.log(this.classlist[index])
            },

            showChecking: function () {
                this.isChecking = true
                this.isCheckingActive = true
                this.isSearch = false
                this.isSearchActive = false
                // this.$refs.mychild
            }
        }
    }
</script>

<style lang="less" scoped>
    .search-class {
        /*border:2px solid red;*/
        text-align: center;
        width: 1000px;
        margin: 50px 0 auto;
        /*margin-top: 50px;*/

        .search-text {
            /*display: inline-block;*/
            /*margin-right: 50px;*/
            margin-left: 300px;
            float:left;
            margin-top: 20px;
            color: #2e6da4;
            font-size: 16px;
            font-weight: bold;
        }

        .search-table {
            display: inline-block;
            text-align: center;

            input {
                width:100px;
                height:30px;
            }
        }

        .search-btn {
            display: inline-block;
            margin-left: 50px;
        }
    }

    .class-info {
        margin-top: 50px;
        text-align: center;
        margin-bottom: 50px;

        table{

            margin:0 auto ;
            thead {
                color: black;
                font-weight: bold;
                font-size: 16px;

                td {
                    /*width: 150px;*/
                    height: 50px;
                    line-height: 50px;
                    background-color: #d0e9c6;
                    border: 1px solid darkgrey;
                }
            }

            td {
                /*width: 150px;*/
                padding: 10px;
                text-align: center;
                height: 50px;
                line-height: 50px;
                border: 1px solid darkgrey;
                white-space: nowrap;
                overflow: hidden;
                text-overflow:ellipsis;
            }
        }

    }

</style>