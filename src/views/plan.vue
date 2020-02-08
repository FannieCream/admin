<template>
    <div>
        <navbar/>
        <div class="show-plan">
            <show_plan/>
        </div>
    </div>
</template>

<script>
    import navbar from "../components/navbar/index"
    import show_plan from "../components/plan/show_plan"
    export default {
        name: "plan",
        components: {
            navbar, show_plan
        }
    }
</script>

<style scoped>
    .show-plan {
        position: absolute;
        top: 20%;
    }

</style>