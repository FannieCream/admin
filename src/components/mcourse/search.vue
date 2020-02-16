<template>
    <div id="mcourse">
<!--        <component :is="checking" ></component>-->
        <checking v-show="isChecking" :class="{'active':isCheckingActive}"></checking>
        <div class="search" v-show="isSearch" :class="{'active':isSearchActive}">
            <div class="search-box">
                <p>检索</p>
                <table>
                    <tr>
                        <td>名称</td>
                        <td>代码</td>
                        <td>老师</td>
                        <td>时间</td>
                        <td>校区</td>
                        <td>地点</td>
                        <td>选修/必修</td>
                    </tr>
                    <tr>
                        <td><input type="text" name="cname"></td>
                        <td><input type="text" name="code"></td>
                        <td><input type="text" name="teacher"></td>
                        <td><input type="text" name="time"></td>
    <!--                    <td><select class="form-control" name="district">-->
    <!--                        <option>不限校区</option>-->
    <!--                        <option>中山北路校区</option>-->
    <!--                        <option>闵行校区</option>-->
    <!--                        </select></td>-->
                        <td><input type="text" name="district"></td>
                        <td><input type="text" name="place"></td>
                        <td><input type="text" name="ctype"></td>
    <!--                    <td><select class="form-control" name="ctype">-->
    <!--                        <option>不限类型</option>-->
    <!--                        <option>选修</option>-->
    <!--                        <option>必修</option>-->
    <!--                    </select></td>-->
                    </tr>
                </table>
                <button type="submit">确认</button>
            </div>

            <div class="search-content">
                <table class="table table-bordered">
                    <thead>
                    <tr>
                        <td>名称</td>
                        <td>代码</td>
                        <td>老师</td>
                        <td>时间</td>
                        <td>校区</td>
                        <td>地点</td>
                        <td>选修/必修</td>
                        <td>课程内容</td>
                        <td>选课名单</td>
                        <td>二维码生成</td>
                    </tr>
                    </thead>
                    <tbody>
                    <tr v-for="item in courselist">
                        <td>{{item.cname}}</td>
                        <td>{{item.code}}</td>
                        <td>{{item.teacher}}</td>
                        <td>{{item.time}}</td>
                        <td>{{item.district}}</td>
                        <td>{{item.place}}</td>
                        <td>{{item.ctype}}</td>
                        <td>{{item.content}}</td>
                        <td><button @click="showChecking" type="button" class="btn btn-primary">点击</button></td>
                        <td><button type="button" class="btn btn-primary">点击</button></td>
                    </tr>
                    </tbody>

                </table>
<!--                <button type="button" class="btn btn-default" style="display: inline-block; ma">修改</button>-->
<!--                <button type="button" class="btn btn-default" style="display: inline-block">确认</button>-->
                <button type="button" class="btn btn-default" style="display: inline-block; margin-left: 5%; margin-right: 20%">修改</button>
                <button type="button" class="btn btn-default" style="display: inline-block">确认</button>

            </div>
        </div>
    </div>
    
</template>

<script>
    import checking from "./checking";
    export default {
        name: "search",
        components: {
            checking
        },

        // el: "#mcourse",
        data() {
            return {
                isChecking: false,
                isCheckingActive: false,
                isSearch: true,
                isSearchActive: false,

                courselist: [
                    {
                        cname: "课程1", code: "1001", teacher: "李老师", time: "1.1",
                        district: "中北校区", place: "文史楼101", ctype: "选修", content: "这是课程内容描述"
                    },
                    {
                        cname: "课程2", code: "1002", teacher: "刘老师", time: "1.10",
                        district: "中北校区", place: "文史楼101", ctype: "必修", content: "这是课程内容描述"
                    },
                    {
                        cname: "课程3", code: "1003", teacher: "张老师", time: "1.12",
                        district: "中北校区", place: "理科大楼101", ctype: "必修", content: "这是课程内容描述"
                    },
                    {
                        cname: "课程4", code: "1004", teacher: "王老师", time: "1.14",
                        district: "中北校区", place: "教书院301", ctype: "选修", content: "这是课程内容描述"
                    }
                ]

            }
        },

        methods: {
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
    .search-box {
        position: absolute;
        left: 30%;
        /*margin-bottom: 50px;*/

    }

    .search-box p {
        float:left;
        margin-right: 30px;
        /*position: absolute;*/
        /*left:-10%*/
    }

    .search-box td {
        width:80px;
        text-align: center;
        padding: 0;
    }

    .search-box input {
        width: 80px;
        padding: 0;
    }

    .search-box button {
        /*float:right;*/
        /*margin-left: 50px;*/
        /*margin-top:-40px;*/
        position: relative;
        left:60%;
    }

    .search-content {
        margin-bottom: 50px;
        /*margin-top: 100px;*/


        table {
            position: absolute;
            margin-top: 100px;
            /*left: 10%;*/
            /*right:10%;*/
            /*flex-direction: row;*/
            /*justify-content: center;*/
            /*display: inline-block;*/

            td {
                padding: 5px;
                text-align: center;
                /*max-width: 30px;*/
                /*width: 30px;*/
                white-space: nowrap;
                overflow: hidden;
                text-overflow:ellipsis;
            }

        }


    }


</style>