<template>
    <div>
        <h2>我是子组件的标题</h2>
        <slot name="head">在没有要分发的内容时才会显示head。</slot>
        <slot name="foot">在没有要分发的内容时才会显示foot。</slot>
    </div>
</template>

<script>
    export default {
        name:'SlotChild1',
        data(){
            return{
                
            }
        }
    }
</script>