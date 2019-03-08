<template>
    <div class="loading" v-loading="loading">
        <h4>Loading...</h4>
        <ul>
            <li v-for="(item,index) in newLists" :key="">{{item.name}}</li>
        </ul>
        <button @click="Loading">Loading...</button>
    </div>
</template>

<script>
    export default {
        name:'Loading',
        data(){
            return{
                loading:false,
                newLists:[],
                lists:{"code":"0000",
                       "data":{
                            "quickProcessMenus":[
                                {
                                    "name":"退",
                                    "subMenus":[
                                        {"name":"退增值业务","url":"/vsop/index"}
                                    ]
                                },
                                {
                                    "name":"返",
                                    "subMenus":[
                                        {"name":"返档","url":"/agent/return-file"}
                                    ]
                                },
                                {
                                    "name":"...",
                                    "subMenus":[
                                                {"name":"卖场交费","url":"/sso-old-system?baseType=mall"},
                                                {"name":"商机","url":"/tools/bo/ssologin"},
                                                {"name":"充值冲正","url":"/shopping-cart/payingwz"},
                                                {"name":"97退单","url":"/97RollBack/index"},
                                                {"name":"单点集团","url":"/business-jt/lte-setToken"}
                                    ]
                                }
                            ]
                        },
                        "message":"成功",
                        "respDate":"2019-03-01 21:12:49",
                        "status":200,
                        "path":"/menu/quickProcess"
                }
            }
        },
        methods:{
            wang(){
                this.loading = true;
                if(this.lists.code==="0000"){
                    let arr = []; 
                    this.lists.data.quickProcessMenus.filter(item => {
                      return arr.push(item.subMenus);
                    });
                    this.newLists = Array.prototype.concat.apply([],arr);
                    this.loading = false;
                }
            },
            Loading:function(){
                let self = this;
                this.loading = true;
                setTimeout(function(){
                    self.loading = false;
                },2000)
            } 
        },
        created(){
            this.wang()
        }
    }
</script>

<style>
    .loading{
        width: 250px;
        height:200px;
        background: #f0f;
    }
    .el-loading-mask{
        /* background: #fff; */
    }
    h4{
        text-align:center;
        margin:0;
    }
</style>