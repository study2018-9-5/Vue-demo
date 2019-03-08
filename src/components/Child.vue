<template>
    <div class="child">
        <h4>子组件</h4>
        <p>初始的值：{{ initValue }}</p>
        <input type="text" v-model="initValue"/>
        <p>子值count:{{ count }}</p>
        <button @click="incrementCount">{{ initValue }}</button>

        <!--初始渲染时是不会更新数据的，要调用一次InitVal-->
        <input type="text" :value="InitVal" hidden> 
    </div>
</template>

<script>
    export default {
        name: 'Button',
        props:['text'], //使用props接收数据
        data(){
            return{
                count:0,
                initValue:''
            }
        },
        methods:{
            incrementCount:function(){
                this.count = this.count + 1

                //通过this.$emit触发自定义事件increment1
                this.$emit('increment1')
            }
        },
        computed:{
            InitVal:function(){
                this.initValue = this.text
            }
        },
        created(){
            
        }
    }
</script>

<style lang="scss" scoped>
    .child{
        width: 240px;
        border: 1px solid #000;
        box-sizing: border-box;
        margin-left: 5px;
        margin-bottom: 5px;
        h4{
            text-align:center;
            margin:0;
        }
        p{
            margin-bottom:5px;
        }
    }
</style>