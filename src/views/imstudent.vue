<template>
    <div>
        <navbar/>
        <div id="import-student">
            <nav class="imstudent-type">
                <ul>
                    <li @click="showBatch" :class="{'active':isBatchActive}">批量导入</li>
                    <li @click="showSingle" :class="{'active':isSingleActive}">逐条导入</li>
                </ul>
            </nav>
            <batch v-show="isBatch"></batch>
            <single v-show="isSingle"></single>

        </div>
    </div>

</template>

<script>
    import navbar from "../components/navbar/index"
    import batch from "../components/imstudent/batch"
    import single from "../components/imstudent/single"
    import select_class from "../components/imstudent/select_class";
    export default {
        name: "imstudent",
        components: {
            navbar, batch, single,  select_class
        },

        el:"#import-student",
        data() {
            return {
                isBatch: true,
                isSingle: false,
                isBatchActive: true,
                isSingleActive: false
            }
        },
        methods: {
            showBatch: function () {
                this.isBatch = true
                this.isBatchActive = true
                this.isSingle = false
                this.isSingleActive = false
            },

            showSingle: function () {
                this.isBatch = false
                this.isBatchActive = false
                this.isSingle = true
                this.isSingleActive = true
            }
        }

    }
</script>

<style lang="less">
    #import-student {
        position: absolute;
        top:20%;
        width: 100%;
        text-align: center;
    }

    .imstudent-type {
        margin-bottom: 50px;

        .active {
            border-bottom: 1px solid black;
        }

        li {
            display: inline-block;
            width:150px;
            text-align: center;

        }


    }
</style>