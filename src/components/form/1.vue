<template>
  <div>这里是汇总信息
  <ul>
      <li>{{total}}</li>
       
      
      <li>{{amount}}</li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
  </ul>
  </div>
</template>
 
<script>
export default {
  
  name: "Total",
  props:['total'],
  data () {
    return {
        amount:this.total
       
    };
  },
//watch很重要。data（）函数只是在初始化的时候会运行一次。所以总是空。而我们异步过来的数据，需要watch他 才能得到。
  watch:{
  total:function(newVal,oldVal){
    this.amount = newVal;
  }
},
  mounted(){
      console.log(this.amount)
  }
 
}

</script>