<template>
    <div>
        <navbar/>
        <div class="show-data">
            <p>this is data page</p>
        </div>
    </div>
</template>

<script>
    import navbar from "@/components/navbar/index"
    // import navbar from "@components/navbar/index"
    export default {
        name: "admin",
        components: {
            navbar
        }
    }
</script>

<style scoped>
    .show-data {
        position: absolute;
        top: 20%;
        width: 100%;
        height: 20px;
        text-align: center;
        font-size: 30px;
        font-family: "Comic Sans MS";
    }

</style>