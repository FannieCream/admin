<template>
    <div>
        <navbar/>
        <div id="manage-course">
            <nav class="mcourse-type">
                <ul>
                <li @click="showSearch" :class="{'active':isSearchActive}">课程检索</li>
                <li @click="showChecking" :class="{'active':isCheckingActive}">课程考勤</li>
                </ul>
            </nav>
            <search v-show="isSearch"></search>
            <checking v-show="isChecking"></checking>
        </div>
    </div>

</template>

<script>
    import navbar from "@/components/navbar/index"
    import search from "@/components/mcourse/search"
    import checking from "@/components/mcourse/checking"
    export default {
        name: "mcourse",
        components:{
            navbar, search, checking
        },

        // el:"#manage-course",
        data() {
            return {
                isSearch: true,
                isSearchActive: true,
                isChecking: false,
                isCheckingActive: false
            }
        },

        methods: {
            showSearch: function() {
                this.isSearch = true
                this.isSearchActive = true
                this.isChecking = false
                this.isCheckingActive = false
            },

            showChecking: function() {
                this.isSearch = false
                this.isSearchActive = false
                this.isChecking = true
                this.isCheckingActive = true
            }

        }
    }
</script>

<style lang="less" scoped>
    #manage-course {
        position: absolute;
        top:20%;
        width:100%;
        text-align: center;

        .active {
            border-bottom: 2px solid darkgreen;
            font-weight: bolder;
            font-size: 18px;
            color: darkgreen;
        }

        li {
            display: inline-block;
            width:150px;
            text-align: center;
            font-size: 16px;
            color: black;
        }

        .mcourse-type {
            margin-bottom: 50px;
        }
    }

</style>