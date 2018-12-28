<template>
    <div class="login">
        <div class="title" >
            <p>用户名：<input type="text"  v-model="userName"></p>
            <p>密码：  <input type="text"  v-model="password"></p> 
            <button @click='ff' v-bind:items="items" >login</button>            
        </div>        
        <Info ref="Info" v-if='op'  v-bind:items="items"></Info>     
    </div>

</template>

<script >
import Info from './Info.vue';
export default {
    // el:"#oth",  
    components:{Info},
    data(){
        return {
            op:false,

             items:["电影","音乐","书籍" ],
     
        }
    },
    methods:{
        ff:function(){     
            this.op=true;
            this.$refs.Info.testzf("我是子组件的方法哟");
        },        
        test:function(){      
           alert('这是一个父组件的方法哟，在子组件中调用父组件方法');          
        }
    } 
}
</script>

<style>
</style>