<template>
    <div>
        <navbar/>
        <div id="import-course">
            <nav class="imcourse-type">
                <ul>
<!--                    <li v-for="(item,$index) in types" @click="selectType(item,$index)":class="{'active':item.active, 'unactive':!item.active}"></li>-->
                    <li @click="showBatch" :class="{'active':isBatchActive}">批量导入</li>
                    <li @click="showSingle" :class="{'active':isSingleActive}">逐条导入</li>
                </ul>
            </nav>
            <batch v-show="isBatch"></batch>
            <single v-show="isSingle"></single>
        </div>

    </div>

</template>

<script type="text/javascript">
    import navbar from "@/components/navbar/index"
    import batch from "@/components/imcourse/batch"
    import single from "@/components/imcourse/single"
    export default {
        name: "imcourse",
        components: {
            navbar, batch, single
        },

        el:"#import-course",
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
    #import-course {
        position: absolute;
        top:20%;
        width: 100%;
        text-align: center;
    }

    .imcourse-type {
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