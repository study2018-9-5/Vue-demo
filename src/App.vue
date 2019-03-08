<template>
  <div id="app">
    <div class="box">
        <parent/>
    </div>
    <div class="box">
        <watch/>
    </div>
    <div class="box">
      
    </div>
    <div class="box"></div>
    <div class="box">
        <dynamic/>
    </div>
    <div class="box">
        <slot-parent/>
    </div>
    <div class="box">
        <loading/>
    </div>
    <div class="box">
        <!-- <w-form/> -->
    </div>



    <!-- 
    <watch/>
    <tab-change/>
    
    
    
    -->
  </div>
</template>

<script>
  import Parent from '@/components/Parent'
  import Watch from '@/components/Watch'
  import TabChange from '@/components/TabChange'
  import Dynamic from '@/components/dynamic/Dynamic' //动态加载组件
  import SlotParent from '@/components/slot/SlotParent' //slot插槽组件
  import Loading from '@/components/elementUi/Loading' //ElemetUI的loading组件
  import Form from '@/components/elementUi/Form.vue' //Form表单的验证
  
  export default {
    name: 'App',
    components: {
      'parent':Parent,
      'watch':Watch,
      'tab-change':TabChange,
      'dynamic':Dynamic,
      'slot-parent':SlotParent,
      'loading':Loading,
      'w-form':Form
    }
  }
</script>

<style lang="scss" scoped>
  *{
    margin:0;
    padding: 0;
  }
  #app{
    width:1040px;
    height: 520px;
    background: red;
    .box{
      width: 250px;
      height: 250px;
      float: left;
      margin-right: 10px;
      margin-bottom: 10px;
      background: #ccc;
    }
  }
</style>
