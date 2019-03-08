<template>
    <div>
        <h4>vue 动态组件实现tab切换加载不同的小模块</h4>
        <div>
            <a href="javascript:void(0)" @click="tabChange(child1)">第一项</a><!--child1是实参-->
            <a href="javascript:void(0)" @click="tabChange(child2)">第二项</a>
            <a href="javascript:void(0)" @click="tabChange(child3)">第三项</a>
        </div>
        
        <!-- 当组件在keep-alive中时，组件中的状态会进入缓存 -->
        <keep-alive>
            <!-- 动态地绑定到它的 is 特性，我们让多个组件可以使用同一个挂载点，并动态切换。-->
            <!-- currentView等于什么组件就渲染什么组件 -->
            <div :is="currentView"></div>
        </keep-alive>
    </div>
</template>

<script>
// 导入子组件
import Child1 from '@/components/dynamic/Child1';
import Child2 from '@/components/dynamic/Child2';
import Child3 from '@/components/dynamic/Child3';

export default {
    name:'Dynamic',
    components: {
        Child1,
        Child2,
        Child3
    },
    data () {
        return {
            child1: 'Child1',
            child2: 'Child2',
            child3: 'Child3',
            currentView: 'Child1' // 默认选中第一项
        };
    },
    methods: {
        tabChange(tabItem) { //tabItem是形参
            console.log(tabItem);
            this.currentView = tabItem;
        }
    }
};
</script>

<style scoped>
    h4{
        text-align: center;
        margin-bottom:15px;
    }
</style>