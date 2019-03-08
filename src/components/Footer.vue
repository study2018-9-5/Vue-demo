<template>
    <footer>{{text}}</footer>
</template>

<script>
export default {
    name: 'w-foot',
    data(){
        return {
            text: '尾部'
        }
    },
    //这里的mouted表示当组件和页面挂载完成的时候，需要执行的函数
    mounted(){ 
        //因为在this.bus.$on内部的this是指向 main.js中的Vue实例的，
        //所以这里，先使用 _this将this存起来，后面就可以使用了。
        var _this = this
        //console.log(this) //this指向VueComponent footer。

        //使用$on监听事件toChangeTitle，这样当header组件中使用emit主动触发了 
        //toChangeTitle事件之后，这里就可以接收到
        this.bus.$on('toChangeTitle', function (title) {
            _this.text = title;
            //console.log(this)
        })
    }
}
</script>