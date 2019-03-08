<template>
    <div class="parent">
        <!--显示total的值-->
        <h4>父组件</h4>
        <p>&nbsp;父值total:{{ total }}</p> 
         
        <!--子组件，(父 => 子)通过 v-bind:(或直接用冒号)传递数据，使用props接收数据-->
        <!--子组件，(子 => 父)通过自定义事件@increment1来触发incrementTotal函数-->
        <child :text="showText" @increment1="incrementTotal"/> 
        <!-- <w-header/>
        <w-footer/> -->
    </div>
</template>

<script>
    import Child from '@/components/Child' //导入子组件
    import Header from '@/components/Header'
    import Footer from '@/components/Footer'
    export default {
        name: 'index',
        components:{
            'child':Child, //注册子组件
            'w-header':Header,
            'w-footer':Footer
        },
        data(){
            return{
                total:0,
                showText: 'AddCount父传子'
            }
        },
        methods:{
            //当incrementTotal被触发时total的值会改变
            incrementTotal:function(){ 
                this.total++
            }
        }

    }
</script>

<style lang="scss" scoped>
    .parent{
        width: 250px;
        border: 1px solid #000;
        box-sizing: border-box;
        h4{
            text-align:center;
            margin:0;
        }
    }
</style>