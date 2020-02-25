<template>
    <div>
        <navbar/>
        <div class="show-student">
            <student/>
        </div>
    </div>
</template>

<script>
    import navbar from "../components/navbar/index"
    import student from "../components/mstudent/student"
    export default {
        name: "mstudent",
        components: {
            navbar, student
        }
    }
</script>

<style lang="less" scoped>
    .show-student {
        position: absolute;
        top:20%;
        width: 100%;
    }

</style>