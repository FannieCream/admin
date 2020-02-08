<template>
    <div class="show-plan-part">
        <table class="table table-bordered" style="margin: auto">
            <tbody>
            <tr>
                <td>必修学分</td>
                <td><p style="width:50px">30</p></td>
            </tr>
            </tbody>
        </table>
        <table class="table table-bordered" style="margin-top: 50px">
            <tbody>
            <tr>
                <td>选修学分</td>
                <td><p style="width:50px">30</p></td>
            </tr>
            </tbody>
        </table>
        <button type="button" class="btn btn-default" style="position: absolute; left: 100%">修改</button>
        <button type="button" class="btn btn-default" style="position: absolute; left: 150%">确认</button>
    </div>
</template>

<script>
    export default {
        name: "show_plan"
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