<template>
    <div id="demo">
        <!-- 点击button时将按钮的index传入changeTab中 -->
        <button v-for="(item,index) in tabs" @click="changeTab(index)" :class="{active:index == num}">{{item}}</button>
        <div class="content" v-for="(content,index) in tabContents" v-if="index===num">{{content}}
            <ul v-if="0===num">
                <li @click="changeContent">{{liContent}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name:'tabChange',
        data(){
            return{
                tabs:["tab1","tab2","tab3"],
                tabContents: ["内容一", "内容二","内容三"],
                num:0,
                liContent:'显示li中的内容'
            }
        },
        methods:{
            changeTab(index){
                this.num = index;
            },
            changeContent(){
                this.liContent = '点击之后显示li中的内容'
            }
        }
    }
</script>

<style>
    #demo{
        width:300px;
        height: 100px;
        /* background: red; */
    }
    .content{
        width: 300px;
        height: 80px;
        background: #ccc;
    }

    button:nth-of-type(2){
        margin-left:-5px;
    }

    .active{
        background: #ff0;
    }
</style>