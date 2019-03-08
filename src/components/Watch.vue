<template>
    <div>
        <h4>watch监听</h4>
        <!-- demoVal:<input v-model="demoVal"> -->
        <p>value:{{value}}</p> 
        <button @click='changeDemo'>点击监听demoVal++</button>
    </div>
</template>

<script>
    export default {
        name:'watch',
        data(){
            return {
                demoVal: 0,
                value: 0
            }
        },
        methods:{
            changeDemo:function(){
                this.demoVal++
            }
        },
        // 当demo的值发生变化时watch会执行其内部函数
        watch:{
            demoVal(){
                this.value = this.demoVal;
            }
        }
    }
</script>

<style lang="scss" scoped>
    h4{
        text-align:center;
        margin-bottom:15px;
    }
</style>