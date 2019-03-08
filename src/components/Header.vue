<template>
    <!-- <header @click="changeTitle">{{title}}</header> -->
    <ul>
        <li @click="changeTitle" v-for='(list,index) in lists'>{{index}}:{{list.li}}</li>
    </ul>
</template>

<script>
    export default {
        name: 'w-head',
        data(){
            return {
                // title: '头部',
                lists:[
                    {li:'第一个li'},
                    {li:'第二个li'},
                    {li:'第三个li'}
                ]
            }
        },
        methods:{
            changeTitle(ev){
                //ev是点击到的标签元素。
                //使用$emit触发toChangeTitle方法，那么$on就可以监听接收这个事件。
                //参数(事件名，传输的值)。
                // this.bus.$emit('toChangeTitle','首页')
                this.bus.$emit('toChangeTitle',ev.target.innerHTML)
            }
        }
    }
</script>