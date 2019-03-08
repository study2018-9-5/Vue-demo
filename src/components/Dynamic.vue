<template>
    <div id="example">
        <button @click="change">切换页面</button>
        <button @click="changeContent">改变内容</button>
        <keep-alive>
            <component :is="currentView"></component>
        </keep-alive>
    </div>
</template>

<script>
    // var home = {template:'<div>我是主页</div>'};
    // var post = {template:'<div>我是提交页</div>'};
    // var archive = {template:'<div>我是存档页</div>'};
    export default {
        name:'dynamic',
        // components:{
        //     home,
        //     post,
        //     archive,
        // },
        data(){
            return{
                index:0,
                arr:[
                    {template:`<div>我是主页</div>`},
                    {template:`<div>我是提交页</div>`},
                    {template:`<div>我是存档页</div>`}
                ],
            }
        },
        computed:{
            currentView(){
                return this.arr[this.index];
            }
        },
        methods:{
            change(){
                this.index = (++this.index)%3;
            },
            changeContent(){
                // console.log(this.arr[0].template)
                this.arr[0].template = '<div>我是主页</div>'
            }
        }
    }
</script>