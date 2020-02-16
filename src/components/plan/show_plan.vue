<template>
    <div class="show-plan-part">
        <table class="table table-bordered" style="margin: auto">
            <tbody>
            <tr>
                <td>必修学分</td>
                <td>{{compulCredit}}</td>
                <td v-show="editSeen"><input type="text" v-model="newCompulCredit"></td>
            </tr>
            </tbody>
        </table>
        <table class="table table-bordered" style="margin-top: 50px">
            <tbody>
            <tr>
                <td>选修学分</td>
                <td>{{optionalCredit}}</td>
                <td v-show="editSeen"><input type="text" v-model="newOptionalCredit"></td>
            </tr>
            </tbody>
        </table>

<!--        <fieldset v-show="editSeen">-->
<!--            <div>-->
<!--                <tr>-->
<!--                    <td>必修学分</td>-->
<!--                    <td><input type="text" v-model="newCompulCredit"></td>-->
<!--                    <td></td>-->
<!--                </tr>-->
<!--                <tr>-->
<!--                    <td>选修学分</td>-->
<!--                    <td><input type="text" v-model="newOptionalCredit"></td>-->
<!--                </tr>-->
<!--                <p>-->
<!--                    <button class="btn btn-success btn-sm submit" @click="editSubmit">提交</button>-->
<!--                </p>-->
<!--            </div>-->
<!--        </fieldset>-->


        <button @click="update" type="button" class="btn btn-default" style="position: absolute; left: 100%">修改</button>
        <button @click="editSubmit" type="button" class="btn btn-default" style="position: absolute; left: 150%">确认</button>
    </div>
</template>

<script>
    export default {
        name: "show_plan",
        data(){
            return {
                editSeen: false,
                compulCredit: 30, //必修课学分
                optionalCredit: 30, //选修学分
                newCompulCredit: this.compulCredit,
                newOptionalCredit:this.optionalCredit
            }
        },

        methods: {
            update: function(){
                this.editSeen = true
            },

            editSubmit: function(){
                this.editSeen = false
                this.compulCredit = this.newCompulCredit
                this.optionalCredit = this.newOptionalCredit

            }

        }
    }

</script>

<style lang="less" scoped>
    .show-plan-part {
        width: 100%;
        margin-left: 400px;
        /*margin-right: auto;*/


        tr {
            margin: 20px 0;
        }

        td {
            padding: 5px 0px;
            text-align: center;
        }

        button {
            margin-top: 30px;
        }
    }

</style>