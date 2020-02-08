<template>
    <div>
        <navbar/>
        <div class="show-admin">
            <show_admin/>
        </div>

    </div>
</template>

<script>
    import navbar from "@/components/navbar/index"
    // import navbar from "@components/navbar/index"
    import show_admin from "@/components/admin/show_admin"
    export default {
        name: "admin",
        components:{
            navbar, show_admin
        }
    }
</script>

<style lang="less" scoped>
    .show-admin {
        position: absolute;
        top:20%;
    }

</style>