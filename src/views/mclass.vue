<template>
    <div id="manage-class">
        <navbar/>
        <div class="show-class">
            <nav>
                <ul>
                    <li @click="showClass" :class="{'active':isClassActive}">班级列表</li>
                    <li @click="showStudent" :class="{'active':isStudentActive}">班级名单</li>
                </ul>
            </nav>
            <classlist v-show="isClass"></classlist>
            <studentlist v-show="isStudent"></studentlist>
        </div>

    </div>
</template>

<script>
    import navbar from "../components/navbar/index"
    import classlist from "../components/mclass/class";
    import studentlist from "../components/mclass/student";
    export default {
        name: "mclass",
        components: {
            studentlist,
            classlist,
            navbar
        },

        el: "#manage-class",
        data() {
            return {
                isClass: true,
                isClassActive: true,
                isStudent: false,
                isStudentActive:false
            }
        },

        methods: {
            showClass: function () {
                this.isClass = true
                this.isClassActive = true
                this.isStudent = false
                this.isStudentActive = false
            },

            showStudent: function () {
                this.isClass = false
                this.isClassActive = false
                this.isStudent = true
                this.isStudentActive = true
            }
        }
    }
</script>

<style lang="less" scoped>
    .show-class {
        position: absolute;
        top:20%;
        left:25%;
        text-align: center;
        margin-bottom: 50px;

        .active {
            border-bottom: 1px solid black;
        }

        li {
            display: inline-block;
            width: 150px;
        }
    }

</style>