<template>
    <div class="single">
        <table>
            <tr>
                <td>学生 </td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>学号 </td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>年级 </td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>一级学院 </td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>入党状态 </td>
                <td><input v-model="name"></td>
            </tr>
            <tr>
                <td>班级 </td>
                <td><select_class></select_class></td>
            </tr>
        </table>
        <button type="submit" style="float: right; margin-top:10px ">确认</button>

    </div>
</template>

<script>
    import select_class from "./select_class";
    export default {
        name: "single",
        components: {
            select_class
        }
    }
</script>

<style lang="less" scoped>
    .single {
        position: absolute;
        left: 40%;

        td {
            text-align: center;
        }
    }

</style>