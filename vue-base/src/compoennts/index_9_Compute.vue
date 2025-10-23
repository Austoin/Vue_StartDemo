<script>
export default {
    data() {
        return {
           cnt: "content",

           austoin: {

            name:'austoin',
            use:['vue', 'python', 'react'],

           }

        }
    },

    methods: {
       isYe(){
            return this.austoin.use.length > 2 ? 'Yes' : 'NO'
        },


    },

    // 虽然methods也能达到计算属性的效果，但计算属性对比methods的优点是缓存更少，不会每次启动程序都计算一遍内容
    computed: {    
        isYes(){
            return this.austoin.use.length > 2 ? 'Yes' : 'NO'
        },

    }
}

</script>

<template>
    <div :class="cnt">
        <h2>计算属性</h2>
        <h3>{{ austoin.name }}</h3>
        <h3>{{ isYes }}</h3> <!-- 计算属性 -->
        <h3>{{ isYe() }}</h3> <!-- 函数方法 -->

        <!-- 复炸的逻辑程序建议使用计算属性，因为一个页面使用多次 isYes 计算属性也是只调用一次，而使用多次 isYe 函数需要调用多次 -->
    </div> 


</template>

<style>

    .content {
        display: flex;
        flex-direction: column;
        align-items: center;   
        justify-content: center;
        
        height: 50vh; 
        border: 1px solid #000;
    }

</style>