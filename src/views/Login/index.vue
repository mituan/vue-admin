<template>
   <div id="login">
       <div class="login-wrap"> 
           <div class="menu-tab">
               <li :class="{'current':item.current}" v-for="item in menuTab" :key="item.id" @click="toggleMenu(item)">{{ item.txt }}</li>
           </div>
       </div>
   </div>
</template>
<script>
export default {
    name:"login",
    data(){
        return{
            menuTab:[
                { txt : '登录', current:false},
                { txt : '注册', current:true}
            ],
        }
    },
    methods:{
        //vue 数据驱动视频渲染
        // js 操纵 dom 元素
        toggleMenu(item){
            this.menuTab.forEach(ele => {
                ele.current = false;
            });
            item.current = true;
        },
    },
    // 挂载完成后自动执行的
    mounted(){},
    created(){},
}
</script>
<style lang="scss" scoped>
#login{
    height: 100vh;
    background-color: #344a5f ;
}

.login-wrap{
    width: 330px;
    margin: auto;
}

.menu-tab {
    text-align: center;
    li{
        display: inline-block;
        width: 88px;
        line-height: 36px;
        font-size: 14px; 
        color: #fff;
        border-radius: 2px;
        cursor: pointer;
    }
    .current {
        background-color: rgba(0,0,0,.1) ;
    }
}
</style>
