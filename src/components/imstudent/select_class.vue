<template>
    <div id="select-class">
        <select v-model="sclass">
            <option v-for="option in options" v-bind:value="option.value">
                {{option.text}}
            </option>
        </select>
    </div>
</template>

<script>
    export default {
        name: "select_class",
        el:"#select-class",
        data() {
            return {
                sclass: "请选择",
                options: [
                    {   text: "青马班（1）班", value: "class one" },
                    {   text: "青马班（2）班", value: "class two" },
                    {   text: "青马班（3）班", value: "class three" },
                    {   text: "青马班（4）班", value: "class four" },
                    {   text: "青马班（5）班", value: "class five" }
                ]

            }
        }
    }
</script>

<style lang="less" scoped>
    #select-class {
        .select {
            /*width:100%;*/
            width: 300px;
            height: 50px;
        }
    }

</style>