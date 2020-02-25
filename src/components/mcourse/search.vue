<template>
    <div id="mcourse">
        <checking v-show="isChecking" :class="{'active':isCheckingActive}"></checking>
        <div class="search" v-show="isSearch" :class="{'active':isSearchActive}">
            <div class="search-box">
                <p>检索</p>
                <table>
                    <thead>
                            <td>名称</td>
                            <td>代码</td>
                            <td>老师</td>
                            <td>时间</td>
                            <td>校区</td>
                            <td>地点</td>
                            <td>选修/必修</td>
                    </thead>
                    <tbody>
                        <tr>
                            <td><input type="text" name="cname"></td>
                            <td><input type="text" name="code"></td>
                            <td><input type="text" name="teacher"></td>
                            <td><input type="text" name="time"></td>
                            <td><select id="district" name="district">
                                <option value="both">不限地区</option>
                                <option value="min">闵行校区</option>
                                <option value="zhong">中山北路校区</option>
                            </select></td>
                            <td><input type="text" name="place"></td>
                            <td><select id="ctype" name="ctype">
                                <option value="both">不限类型</option>
                                <option value="min">选修</option>
                                <option value="zhong">必修</option>
                            </select></td>
                        </tr>
                    </tbody>
                </table>
                <button type="submit" class="btn btn-warning">确认</button>
            </div>

            <div class="search-content">
                <table class="table table-striped">
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

                <div class="pager" id="pager">
          <span class="form-inline">
            <select class="form-control" v-model="pagesize" v-on:change="showPage(pageCurrent,$event,true)" number>
              <option value="10">10</option>
              <option value="20">20</option>
              <option value="30">30</option>
              <option value="40">40</option>
            </select>
          </span>
                    <span v-for="item in pageCount+1">
            <span v-if="item==1" class="btn btn-default" v-on:click="showPage(1,$event)" :class="{'disabled':fDisabled}">
              首页
            </span>
            <span v-if="item==1" class="btn btn-default" v-on:click="showPage(pageCurrent-1,$event)" :class="{'disabled':fDisabled}">
              上一页
            </span>
            <span v-if="item==1" class="btn btn-default" v-on:click="showPage(item,$event)">
              {{item}}
            </span>
            <span v-if="item==1&&item<showPagesStart-1" class="btn btn-default disabled">
              ...
            </span>
            <span v-if="item>1&&item<=pageCount-1&&item>=showPagesStart&&item<=showPageEnd&&item<=pageCount" class="btn btn-default" v-on:click="showPage(item,$event)">
              {{item}}
            </span>
            <span v-if="item==pageCount&&item>showPageEnd+1" class="btn btn-default disabled">
              ...
            </span>
            <span v-if="item==pageCount" class="btn btn-default" v-on:click="showPage(item,$event)" >
              {{item}}
            </span>
            <span v-if="item==pageCount" class="btn btn-default" v-on:click="showPage(pageCurrent+1,$event)" :class="{'disabled':lDisabled}">
              下一页
            </span>
            <span v-if="item==pageCount" class="btn btn-default" v-on:click="showPage(pageCount,$event)" :class="{'disabled':lDisabled}">
              尾页
            </span>
          </span>
                    <span>{{pageCurrent}}/{{pageCount}}</span>
                </div>
<!--                <div class="eg">-->
<!--                <div class="m-style M-box"></div>-->
<!--                <p class="tips">当前是第<span class="now"></span>页</p>-->
<!--                </div>-->
            </div>
        </div>
    </div>
    
</template>

<script type="javascript">
    import checking from "./checking";
    import $ from "jquery"
    export default {
        name: "search",
        components: {
            checking
        },

        data() {
            return {
                // 切换操作
                isChecking: false,
                isCheckingActive: false,
                isSearch: true,
                isSearchActive: false,

                //分页数据
                //为第一页或者最后一页时，首页，尾页不能点击
                fDisabled:false,
                lDisabled:false,
                //总项目数
                totalCount: 100,
                //分页数
                pageCount: 10,
                //当前页面
                pageCurrent: 1,
                //分页大小
                pagesize: 10,
                //显示分页按钮数
                showPages: 11,
                //开始显示的分页按钮
                showPagesStart: 1,
                //结束显示的分页按钮
                showPageEnd: 100,

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
            },
            showPage(pageIndex, $event, forceRefresh){
                if (pageIndex > 0) {
                    if (pageIndex > this.pageCount) {
                        pageIndex = this.pageCount;
                    }
                    //判断数据是否需要更新
                    var currentPageCount = Math.ceil(this.totalCount / this.pagesize);
                    if (currentPageCount != this.pageCount) {
                        pageIndex = 1;
                        this.pageCount = currentPageCount;
                    }
                    else if (this.pageCurrent == pageIndex && currentPageCount == this.pageCount && typeof (forceRefresh) == "undefined") {
                        console.log("not refresh");
                        return;
                    }
                    //处理分页点中样式
                    var buttons = $("#pager").find("span");
                    for (var i = 0; i < buttons.length; i++) {
                        if (buttons.eq(i).html() != pageIndex) {
                            buttons.eq(i).removeClass("active");
                        }
                        else {
                            buttons.eq(i).addClass("active");
                        }
                    }
                    //测试数据 随机生成的
                    var newPageInfo = [];
                    var time=new Date();
                    for (var i = 0; i < this.pagesize; i++) {
                        newPageInfo[newPageInfo.length] = {
                            timestamp: time,
                            count: (i + (pageIndex - 1) * 20)
                        };
                    }
                    this.pageCurrent = pageIndex;
                    // this.courselist = newPageInfo;
                    //如果当前页首页或者尾页，则上一页首页就不能点击，下一页尾页就不能点击
                    if(this.pageCurrent===1){
                        this.fDisabled=true;
                    }else if(this.pageCurrent===this.pageCount){
                        this.lDisabled=true;
                    }else{
                        this.fDisabled=false;
                        this.lDisabled=false;
                    }
                    //计算分页按钮数据
                    if (this.pageCount > this.showPages) {
                        if (pageIndex <= (this.showPages - 1) / 2) {
                            this.showPagesStart = 1;
                            this.showPageEnd = this.showPages - 1;
                            console.log("showPage1")
                        }
                        else if (pageIndex >= this.pageCount - (this.showPages - 3) / 2) {
                            this.showPagesStart = this.pageCount - this.showPages + 2;
                            this.showPageEnd = this.pageCount;
                            console.log("showPage2")
                        }
                        else {
                            console.log("showPage3")
                            this.showPagesStart = pageIndex - (this.showPages - 3) / 2;
                            this.showPageEnd = pageIndex + (this.showPages - 3) / 2;
                        }
                    }
                    console.log("showPagesStart:" + this.showPagesStart + ",showPageEnd:" + this.showPageEnd + ",pageIndex:" + pageIndex);
                }
            }
        },

        mounted(){
            this.showPage(this.pageCurrent, null, true);
        },
        computed:{
        }

       // mounted: function() {
       //     $('.M-box').pagination({
       //         callback: function (api) {
       //             $('.now').text(api.getCurrent());
       //         }
       //     }, function (api) {
       //         $('.now').text(api.getCurrent());
       //     });
       // }
    }
</script>

<style lang="less" scoped>
    #mcourse {
        margin-bottom: 50px;
    }

    .search-box {
        /*border: 2px solid red;*/
        width: 900px;
        margin: 0 auto;
        margin-bottom: 100px;

        p {
            float:left;
            margin-right: 30px;
            margin-top: 20px;
            color: #2e6da4;
            font-size: 16px;
            font-weight: bold;
            /*position: absolute;*/
            /*left:-10%*/
        }

        button {
            float: right;
            margin-top: -35px;
        }

        td {
            width:80px;
            text-align: center;
            padding: 0;
        }

        input, select {
            width: 100px;
            height: 30px;
            padding: 0 5px;
        }
    }

    .search-content {
        margin-bottom: 50px;
        /*margin-top: 100px;*/

        table {
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

    .pager {
        margin-top: 50px;
        margin-bottom: 50px;
    }


</style>