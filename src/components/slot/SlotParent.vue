<template>
    <div>
        <h1>我是父组件</h1>
        <slot-child1>
            <p slot="head">1.主要内容的一个段落1。</p>
            <p slot="foot">2.主要内容的一个段落2。</p>
        </slot-child1>
    </div>
</template>

<script>
    import SlotChild1 from '@/components/slot/SlotChild1'
    export default {
        name:'SlotParent',
        components:{
            'slot-child1':SlotChild1
        },
        data(){
            return{

            }
        },
    }
</script>